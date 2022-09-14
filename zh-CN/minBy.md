---
title: 根据函数获取最小数组值(Min array value based on function)
tags: math,array
expertise: beginner
cover: blog_images/digital-nomad-9.jpg
firstSeen: 2018-01-11T12:25:54+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 在使用提供的函数将每个元素映射到一个值之后，返回数组的最小值。
> Returns the minimum value of an array, after mapping each element to a value using the provided function.

- 使用 `Array.prototype.map()` 将每个元素映射到 `fn` 返回的值。
- 使用 `Math.min()` 获取最小值。

```js
const minBy = (arr, fn) =>
  Math.min(...arr.map(typeof fn === 'function' ? fn : val => val[fn]));
```

```js
minBy([{ n: 4 }, { n: 2 }, { n: 8 }, { n: 6 }], x => x.n); // 2
minBy([{ n: 4 }, { n: 2 }, { n: 8 }, { n: 6 }], 'n'); // 2
```
