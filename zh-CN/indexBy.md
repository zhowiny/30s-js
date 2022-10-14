---
title: 根据函数从数组创建对象(Index array based on function)
tags: array,object
expertise: intermediate
author: chalarangelo
cover: blog_images/guitar-living-room.jpg
firstSeen: 2021-06-20T05:00:00-04:00
---

# 从数组创建对象，使用函数将每个值映射到键。
> Creates an object from an array, using a function to map each value to a key.

- 使用 `Array.prototype.reduce()` 从 `arr` 创建一个对象。
- 将 `fn` 应用于 `arr` 的每个值以生成一个键并将键值对添加到对象中。

```js
const indexBy = (arr, fn) =>
  arr.reduce((obj, v, i) => {
    obj[fn(v, i, arr)] = v;
    return obj;
  }, {});
```

```js
indexBy([
  { id: 10, name: 'apple' },
  { id: 20, name: 'orange' }
], x => x.id);
// { '10': { id: 10, name: 'apple' }, '20': { id: 20, name: 'orange' } }
```
