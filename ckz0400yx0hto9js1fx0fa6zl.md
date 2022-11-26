# Multi-Client & Sentinel Redis Setup with NestJS

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