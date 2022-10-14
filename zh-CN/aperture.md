---
title: 连续元素子数组(Consecutive element subarrays)
tags: array
expertise: intermediate
author: chalarangelo
cover: blog_images/camera-zoom.jpg
firstSeen: 2020-05-13T13:25:33+03:00
lastUpdated: 2020-10-18T20:24:28+03:00
---

# 创建一个连续元素的`n`元组数组。
> Creates an array of `n`-tuples of consecutive elements.

- 使用 `Array.prototype.slice()` 和 `Array.prototype.map()` 创建一个适当长度的数组。
- 使用来自 `arr` 的连续元素的 `n` 元组填充数组。
- 如果 `n` 大于 `arr` 的长度，则返回一个空数组。

```js
const aperture = (n, arr) =>
  n > arr.length
    ? []
    : arr.slice(n - 1).map((v, i) => arr.slice(i, i + n));
```

```js
aperture(2, [1, 2, 3, 4]); // [[1, 2], [2, 3], [3, 4]]
aperture(3, [1, 2, 3, 4]); // [[1, 2, 3], [2, 3, 4]]
aperture(5, [1, 2, 3, 4]); // []
```
