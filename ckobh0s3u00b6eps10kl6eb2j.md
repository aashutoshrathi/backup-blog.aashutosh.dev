---
title: "Own your Setup for Side Projects"
seoTitle: "Deploy Side Projects on EC2 [GUIDE]"
seoDescription: "Roll your VM with all your side project running on custom domains with SSL (includes setting up nginx & certbot setup)"
datePublished: Sat May 01 2021 13:01:17 GMT+0000 (Coordinated Universal Time)
cuid: ckobh0s3u00b6eps10kl6eb2j
slug: cloud-vm-setup
tags: dns, ssl, aws, nginx, nodejs

---

Let's start by talking about side projects, we all start them and some of us finish a few too 😛. But most of the side projects are for fun/PoC and end up getting deployed on free services like Heroku/Glitch for backend or Vercel/Netlify for frontend.

And those are a great set of services to start with, in fact, tools that host static sites rarely ask for money for features like 100% uptime (duh!) and SSL for custom domains, but for services that hosts your servers for you, sooner or later will find a way to ask for money.

Context switching closer to the post title, recently one of my Node Servers which was hosted on Heroku (surviving on [GitHub Student Pack Credits](https://education.github.com/pack) ❤ on Hobby Plan) lost the ability to use SSL with a custom domain 😟, as Heroku doesn't allow you to use a custom domain with SSL on free plans.

This was a trigger and I decided to take an EC2 instance (you can take a similar machine on GCP, Azure, DigitalOcean, etc.) and set up all my servers there themselves with custom domains (yes! with SSL).

## Let's begin!

### ☁ Setup your EC2 Instance (or similar instances)

1. Make an AWS account and get a free tier VM, I have suggested some options below:
    - **AMI** -> Ubuntu Server 20.04 LTS (HVM), SSD Volume Type (64-bit (x86))
    - **Instance Type** -> Choose `t2.micro`
    - **Rest is almost default** which is 8GB storage & 1GB RAM
    - Also, you can whitelist Traffic Type, Port and IPs in Security Group Step and Launch the Instance.

2. Generate a key pair and download the `pem` file and store it safely.
3. To connect to your VM using SSH, you now need to run a command like
```sh
ssh -i "my.pem" ubuntu@<public-dns-of-ec2-instance>
```
That almost wraps part of the things we will do in the browser. 🙆🏻‍♂️

### **[BONUS] ✨ Connect from VS Code**
<img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1619959748173/3ZDuLyQj7.png" style="display: block; margin: 0 auto;" />

- Add an entry in your `~/.ssh/config` as below:
```yaml
Host machineName
    User ubuntu
    HostName <public-dns-of-ec2-instance>
    IdentityFile <path-to-my.pem-file>
```
- Install  [Remote-SSH](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh)
- Press <kbd>Ctrl/Cmd</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd> and write `Connect to Host`
- Select `machineName` and it's done! 🤝🏻

### 📦 Configure your machine

- First things first, the machine comes with Ubuntu 20, but we might need more stuff, so lets update the package lists

```sh
sudo apt-get update
```

- Next is I'll recommend creating a separate folder and then clone the repos you want to host.
- For ease generate SSH Key and add it to GitHub, for generation use these commands and output is your public SSH Key.

```sh
ssh-keygen -t ed25519 -C "your-github-email"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
cat ~/.ssh/id_ed25519.pub
```
- Now install all the dependencies that you'll need (unless using docker images), I'll show a few below
    - Node 14.x
```bash
curl -sL https://deb.nodesource.com/setup_14.x -o nodesource_setup.sh
sudo bash nodesource_setup.sh
sudo apt install -y nodejs
node -v
```
    - pm2 (process manager for keeping your servers running)
```shell
sudo npm i -g pm2
```

### ⚒ Install nginx & certbot

-  [nginx or NginX](https://www.nginx.com/), is a web server that can also be used as a reverse proxy, load balancer, mail proxy, and HTTP cache.
We'll quickly install and enable it.
```sh
sudo apt install nginx
sudo systemctl enable nginx
sudo systemctl start nginx
```

- **certbot** 🤖 is a tool which generates free & legit SSL Certs 🔐 using [LetsEncrypt](https://letsencrypt.org/getting-started/), it also has features auto-renew.
We'll install certbot service and nginx plugin for the same

```sh
sudo apt-get install certbot # for certbot
sudo apt-get install python3-certbot-nginx # for python plugin
```
We are all ready with dependencies, now we'll move to the final steps.

### 👨🏻‍💻 Starting your applications and Adding Domains

- Now you need to start your servers either on `gunicorn` or `pm2` as per your need.
To start with pm2, say your program starts with `npm run start`, then use

```sh
pm2 start "npm run start" --name "your-api"
```
At this stage if your API runs on say port `1337`, you can access the API at `http://<public-ip-of-instance>:1337`

Now let's add the domain to it.
For that first, you need to make a DNS Record Entry.
```
Type: A
Name: `@`(if you want to use domain) else `subdomain`
Value: <public-ip-of-ec2-instance>
TTL: as per your requirement
```

Once this entry is created, now we need to generate SSL Cert and Private key on our side.

Generate a certificate for your domain/subdomain using the command below and answer the prompts as needed
```sh
sudo certbot certonly --nginx
```
This command finished by creating two files at 
```
/etc/letsencrypt/live/<your-domain>/fullchain.pem
/etc/letsencrypt/live/<your-domain>/privkey.pem
```

Now let's set up Nginx for your server
Suppose you want to run your server running on 1337 port on `your-domain`, then 
```sh
cd /etc/nginx/sites-available
nano your-domain.conf
```
Now few things, we first create the file in `sites-available` so that we don't mess up directly with nginx, once we test the config, then we create a soft link to the same in `sites-enabled` which is where nginx looks up while mapping requests.

In your-domain.conf, add the following content and replace `<your-domain>`

```
server {
    listen 80;
    listen 443 ssl;
    server_name <your-domain>;

    ssl_certificate /etc/letsencrypt/live/<your-domain>/fullchain.pem;
    ssl_certificate_key  /etc/letsencrypt/live/<your-domain>/privkey.pem;

    location / {
        proxy_pass http://localhost:1337;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}
```

Now let's make a soft link as promised
```
cd /etc/nginx/sites-enabled
sudo ln -s ../sites-available/your-domain.conf .
```

After you are done with this, let's test our conf file ✅
```
sudo nginx -t
```
if all is well, you can signal nginx to reload configs
```
sudo nginx -s reload
```

Now your API can be accessed at `your-domain` 🎉

So, you have completed a one-time setup of your EC2 instance and deployed one of your APIs on a custom domain.

In the same way, you can add as many side projects as you want to the same machine and redirect internally to another port.