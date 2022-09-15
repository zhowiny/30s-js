---
title: 省略对象属性(Omit object properties)
tags: object
expertise: intermediate
cover: blog_images/broken-screen.jpg
firstSeen: 2018-01-19T13:14:46+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 省略与对象中给定键对应的键值对。
> Omits the key-value pairs corresponding to the given keys from an object.

- 使用 `Object.keys()`、`Array.prototype.filter()` 和 `Array.prototype.includes()` 删除提供的键。
- 使用 `Array.prototype.reduce()` 将过滤后的键转换回具有相应键值对的对象。

```js
const omit = (obj, arr) =>
  Object.keys(obj)
    .filter(k => !arr.includes(k))
    .reduce((acc, key) => ((acc[key] = obj[key]), acc), {});
```

```js
omit({ a: 1, b: '2', c: 3 }, ['b']); // { 'a': 1, 'c': 3 }
```
