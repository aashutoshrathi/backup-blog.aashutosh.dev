---
title: "Netlify's build clean-up"
datePublished: Sat Jun 01 2024 11:09:04 GMT+0000 (Coordinated Universal Time)
cuid: clww0fzxu000309l09ie88x4p
slug: netlifys-build-clean-up
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/VjWi56AWQ9k/upload/fe62b51428798f75cc4e9a32c9d76764.jpeg
tags: build, frontend-development, netlify, vocs

---

On a fine day in boiling Northern India (*thanks* ***El Niño***), I was building a [vocs](https://vocs.dev/) project at work and deploying it to Netlify as a **static build** (*what could go wrong, no?*)

As soon as it deployed, things looked fine at first look, but it was not working as expected, on inspecting it a little, I found that some **assets were not loading properly** and the **search wasn't working** too, but interestingly the same thing works perfectly if I build it manually and deploy the `dist` folder using "[Netlify Drop](https://app.netlify.com/drop)" (*underrated feature btw!*).

I was in the middle of the workday not wanting to spend more than 10 mins on this build. So, I did what I did best, brute force, I started comparing build files of automated builds and manual upload builds.  
Within a matter of seconds, I realized uh oh, the first folder, doesn't exist when I build with CI automation. What was it? 🥁 `.vocs` directory. And guess what? the directory was responsible for keeping the search index and a few assets. (*BINGO!*)

I went down this rabbit hole of "Who allowed Netlify to remove files from my build?".  
Ah! It turns out they accepted that they [remove all the dotfiles/folders from the publish directory, except `.well-known`](https://answers.netlify.com/t/netlify-deploy-api-removes-files-and-directories-beginning-with-a-period/37728) And, [*it's not very well-known why we need it.*](https://serverfault.com/questions/795467/what-is-the-purpose-of-the-well-known-folder)

Since there were no direct ways to get what I wanted, I did some hacks as suggested on forums and on intuition about what I could do in the least time.

* ⚒️ Build Command changed from `yarn build` to `yarn build && mv docs/dist/.vocs docs/dist/dotvocs && mv _redirects docs/dist/_redirects` (*basically renamed the dot folder*)
    
* ⏩ And also added `_redirects` file to forward all my requests coming to `.vocs` folder to `dotvocs` (*my new directory*)
    
    ```bash
    /.vocs/*  /dotvocs/:splat 200!
    ```
    

And BAM!! we have it all working smoothly.

Hope this helps someone! 🖖🏻