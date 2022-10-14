---
title: 映射数组平均值(Mapped array average)
tags: math,array
expertise: intermediate
cover: blog_images/rock-climbing.jpg
firstSeen: 2018-01-11T12:25:54+02:00
lastUpdated: 2020-10-21T21:17:45+03:00
---

# 在使用提供的函数将每个元素映射到一个值之后，计算数组的平均值。
> Calculates the average of an array, after mapping each element to a value using the provided function.

- 使用 `Array.prototype.map()` 将每个元素映射到 `fn` 返回的值。
- 使用 `Array.prototype.reduce()` 将每个值添加到累加器，初始化为 `0`。
- 将结果数组除以其长度。

```js
const averageBy = (arr, fn) =>
  arr
    .map(typeof fn === 'function' ? fn : val => val[fn])
    .reduce((acc, val) => acc + val, 0) / arr.length;
```

```js
averageBy([{ n: 4 }, { n: 2 }, { n: 8 }, { n: 6 }], o => o.n); // 5
averageBy([{ n: 4 }, { n: 2 }, { n: 8 }, { n: 6 }], 'n'); // 5
```
