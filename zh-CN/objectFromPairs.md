---
title: 键值对数组转换为对象(Object from pairs)
tags: object,array
expertise: beginner
cover: blog_images/silver-flat-screen.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 从给定的键值对创建一个对象。
> Creates an object from the given key-value pairs.

- 使用 `Array.prototype.reduce()` 创建和组合键值对。
- [`Object.fromEntries()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/fromEntries) 提供了类似的功能。

```js
const objectFromPairs = arr =>
  arr.reduce((a, [key, val]) => ((a[key] = val), a), {});
```

```js
objectFromPairs([['a', 1], ['b', 2]]); // {a: 1, b: 2}
```
