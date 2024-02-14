# @craftnotion/adonis5-advance-redis-rpc
> Adonis, Adonis 5, Redis RPC

[![npm-image]][npm-url] [![license-image]][license-url] [![typescript-image]][typescript-url]

Advance RPC Provider for Adonisjs, based on Redis pub/sub transport

## Installation
Setup redis from [this manual](https://docs.adonisjs.com/guides/redis)

and

```bash
npm i @craftnotion/adonis5-advance-redis-rpc
node ace invoke @craftnotion/adonis5-advance-redis-rpc
```


## Usage

### Server mode
```ts
import RedisRPC from '@ioc:Adonis/Addons/RedisRPC'
await RedisRPC.server('example') //Create a server with name example

RedisRPC.addHandler('exampleMethod', async ({ data }) => {
  console.log(data);
})
```

### Client mode
```ts

import Route from '@ioc:Adonis/Core/Route'
import RedisRPC from '@ioc:Adonis/Addons/RedisRPC'

Route.get('example', () => {
  await RedisRPC.client()
  const result =  await RedisRPC.call('example.exampleMethod', { data: 'message' });
  return result
})
```

[npm-image]: https://img.shields.io/npm/v/@craftnotion/adonis5-advance-redis-rpc.svg?style=for-the-badge&logo=npm
[npm-url]: https://www.npmjs.com/package/@craftnotion/adonis5-advance-redis-rpc "npm"

[license-image]: https://img.shields.io/npm/l/@craftnotion/adonis5-advance-redis-rpc?color=blueviolet&style=for-the-badge
[license-url]: LICENSE.md "license"

[typescript-image]: https://img.shields.io/badge/Typescript-294E80.svg?style=for-the-badge&logo=typescript
[typescript-url]:  "typescript"
