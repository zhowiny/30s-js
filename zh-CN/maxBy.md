---
title: 根据函数获取最大数组值(Max array value based on function)
tags: math,array
expertise: beginner
cover: blog_images/digital-nomad-4.jpg
firstSeen: 2018-01-11T12:25:54+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

# 在使用提供的函数将每个元素映射到一个值之后，返回数组的最大值。
> Returns the maximum value of an array, after mapping each element to a value using the provided function.

- 使用 `Array.prototype.map()` 将每个元素映射到 `fn` 返回的值。
- 使用 `Math.max()` 获取最大值。

```js
const maxBy = (arr, fn) =>
  Math.max(...arr.map(typeof fn === 'function' ? fn : val => val[fn]));
```

```js
maxBy([{ n: 4 }, { n: 2 }, { n: 8 }, { n: 6 }], x => x.n); // 8
maxBy([{ n: 4 }, { n: 2 }, { n: 8 }, { n: 6 }], 'n'); // 8
```
