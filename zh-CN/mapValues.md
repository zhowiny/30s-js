---
title: 映射对象值(Map object values)
tags: object
expertise: intermediate
cover: blog_images/feathers.jpg
firstSeen: 2018-01-11T20:33:14+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 使用提供的函数映射对象的值，生成具有相同键的新对象。
> Maps the values of an object using the provided function, generating a new object with the same keys.

- 使用 `Object.keys()` 来迭代对象的键。
- 使用 `Array.prototype.reduce()` 创建一个具有相同键和映射值的新对象，使用 `fn`。

```js
const mapValues = (obj, fn) =>
  Object.keys(obj).reduce((acc, k) => {
    acc[k] = fn(obj[k], k, obj);
    return acc;
  }, {});
```

```js
const users = {
  fred: { user: 'fred', age: 40 },
  pebbles: { user: 'pebbles', age: 1 }
};
mapValues(users, u => u.age); // { fred: 40, pebbles: 1 }
```
