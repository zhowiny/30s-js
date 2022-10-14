---
title: 映射对象键(Map object keys)
tags: object
expertise: intermediate
cover: blog_images/rocky-mountains-2.jpg
firstSeen: 2018-01-11T20:33:14+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

# 使用提供的函数映射对象的键，生成一个新对象。
> Maps the keys of an object using the provided function, generating a new object.

- 使用 `Object.keys()` 来迭代对象的键。
- 使用 `Array.prototype.reduce()` 创建一个具有相同值和映射键的新对象，使用 `fn`。

```js
const mapKeys = (obj, fn) =>
  Object.keys(obj).reduce((acc, k) => {
    acc[fn(obj[k], k, obj)] = obj[k];
    return acc;
  }, {});
```

```js
mapKeys({ a: 1, b: 2 }, (val, key) => key + val); // { a1: 1, b2: 2 }
```
