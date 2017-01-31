# Bookshelf Cache Redis
🔥  A robust, performance-focused caching solution for Bookshelf based on top of Redis.

## Installation

```bash
$ cd myProject/
$ npm install bookshelf-cache-redis --save
```

## Usage

```javascript
import config from './knexfile';
import knex from 'knex';
import Bookshelf from 'bookshelf';
import redisCache from 'bookshelf-redis-cache';

const bookshelf = Bookshelf(knex(config));

bookshelf.plugin(redisCache);
```

You can pass the exact same parameters on the `fetchCache` and `fetchAllCache` methods as you will do with `fetch` and `fetchAll`. However, you need to specify an unique serial key for each request.

```javascript

Car
 .forge(params)
 .fetchCache({
   serial: 'car_fetch',
   withRelated: ['engine']
 })
 .orderBy('-productionYear') // Same as .orderBy('cars.productionYear', 'DESC')
 .then(function (results) {
    console.log(results);
 });
```
