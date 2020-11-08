[![NPM version](https://img.shields.io/npm/v/@10xcompany/nest-redis.svg)](https://www.npmjs.com/package/@10xcompany/nest-redis)
[![Downloads](https://img.shields.io/npm/dm/@10xcompany/nest-redis.svg)](https://www.npmjs.com/package/@10xcompany/nest-redis)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)

## Description

The [Redis](https://github.com/luin/ioredis) module for [NestJS](https://github.com/nestjs/nest).

## 🚀 Quick Start

First install the module via `yarn` or `npm` and do not forget to install the database driver as well:

```bash
$ yarn add @10xcompany/nest-redis ioredis
```

or

```bash
$ npm i -s @10xcompany/nest-redis ioredis
```

Once the installation process is completed, we can import the `RedisModule` into the required module or in global scope in `AppModule`.

```typescript
import {RedisModule} from '@10xcompany/nest-redis';

@Module({
  imports: [
    RedisModule.forRoot({
      name: 'foo',
      host: 'localhost',
      port: 6379,
      password: 'neo4j',
      db: 'neo4j',
    }),
  ],
  // ...
})
export class CustomModule {}
```

Or, if you want to use it in global:

```typescript
import {RedisModule} from '@10xcompany/nest-redis';

@Module({
  imports: [
    Neo4jModule.forRoot({
      name: 'foo',
      host: 'localhost',
      port: 6379,
      password: 'neo4j',
      db: 'neo4j',
    }),
  ],
  // ...
})
export class AppModule {}
```

Or, if you're using the Async provider:

```typescript
import {RedisModule} from '@10xcompany/nest-redis';

@Module({
  imports: [
    RedisModule.forRootAsync({
      // ...
      useFactory: () => ({
        name: 'foo',
        host: 'localhost',
        port: 6379,
        password: 'neo4j',
        db: 'neo4j',
      }),
    }),
  ],
  // ...
})
export class CustomModule {}
```

The `forRoot()/forRootAsync()` method accepts the same configuration object as `new Redis()` from the ioredis package.

Afterward, the `RedisService` will be available to inject across entire project or the module which the `RedisModule` is used.

```ts
import {RedisService} from '@10xcompany/nest-redis';

@Injectable()
export class MyService {
  constructor(private readonly redisService: RedisService) {}
}
```

## 📚 Example usage

```typescript
@Injectable()
export class ExampleService {
  constructor(private readonly redisService: RedisService) {}

  async create(): Promise<void> {
    await this.redisService.getClient().set('some-id', 'some-value', 'EX');
  }

  async delete(): Promise<void> {
    await this.redisService.getClient().del('some-id');
  }

  async get(id: string): Promise<QueryResult> {
    await this.redisService.getClient().get('some-id');
  }
}
```

## `RedisService` methods

The `RedisService` exposes few methods for several use case:

- `getClient(): Redis`: method to expose the ioredis instance.

- `getClients(): Map<string, Redis>`: method to get all redis instance

## 🤝 Contributing

Contributions, issues and feature requests are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on the process for submitting pull requests to us.

## Authors

👤 **Quadri Adekunle**

- Github: [@Quadriphobs1](https://github.com/Quadriphobs1)

See also the list of contributors who [participated](https://github.com/10xcompany/redis/contributors) in this project.

## Show Your Support

Please ⭐️ this repository if this project helped you!

## 📝 License

Copyright © 2020.

This project is licensed under the MIT License - see the [LICENSE file](LICENSE) for details.
