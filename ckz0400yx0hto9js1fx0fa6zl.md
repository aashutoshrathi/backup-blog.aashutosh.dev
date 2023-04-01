---
title: "Multi-Client & Sentinel Redis Setup with NestJS"
seoTitle: "Multi-Client & Sentinel Redis Setup with NestJS"
seoDescription: "Setup Multi-Sentinel Multi-client Redis connections with NestJS"
datePublished: Sat Jan 29 2022 17:29:30 GMT+0000 (Coordinated Universal Time)
cuid: ckz0400yx0hto9js1fx0fa6zl
slug: multi-client-and-sentinel-redis-setup-with-nestjs
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1643477341099/VvuNNrh7I.png
tags: redis, typescript, nest

---

There's already a package out there [nestjs-redis](https://github.com/skunight/nestjs-redis), it is a wrapper around [ioredis](https://www.npmjs.com/package/ioredis) and quite easy to use.

There is only one issue you'll face with the package is while wrapping over `ioredis` the devs kept the key `name` for the *sentinel name* and the same name is used for `client/connection name` as per the implementation of the parent package.

I have fixed the same issue in [forked repo](https://github.com/aashutoshrathi/nestjs-redis).

The example config to connect to multi-sentinel name-based setup is below:
```json
[
  {
    "clientName": "sentinelDB5",
    "sentinels": [
      {
        "host": "localhost",
        "port": 6380
      },
      {
        "host": "localhost",
        "port": 6381
      }
    ],
    "db": 5,
    "name": "hahaCluster",
    "password": "topSecret"
  }
]
```

After connecting with this config you can call the following in your services to get clients for these sentinels
```ts
const client = await this.redisService.getClient('sentinelDB5');
```

That's all, now you can go back to hacking as usual 🖖🏻