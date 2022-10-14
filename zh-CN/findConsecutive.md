---
title: 连续元素的数组(Arrays of consecutive elements)
tags: array
expertise: intermediate
author: chalarangelo
cover: blog_images/colorful-pots.jpg
firstSeen: 2022-04-06T05:00:00-04:00
---

# 查找所有连续元素的数组。
> Finds all arrays of consecutive elements.

- 使用 `Array.prototype.slice()` 创建一个数组，从一开始就删除了 `n - 1` 个元素。
- 使用 `Array.prototype.map()` 和 `Array.prototype.slice()` 将每个元素映射到 `n` 个连续元素的数组。

```js
const findConsecutive = (arr, n) =>
  arr.slice(n - 1).map((v, i) => arr.slice(i, i + n));
```

```js
findConsecutive([1, 2, 3, 4, 5], 2);
// [[1, 2], [2, 3], [3, 4], [4, 5]]
```
