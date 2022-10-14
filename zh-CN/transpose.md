---
title: 转置矩阵(Transpose matrix)
tags: array
expertise: intermediate
author: chalarangelo
cover: blog_images/painters-desk.jpg
firstSeen: 2022-04-20T05:00:00-04:00
---

# 转置一个二维数组。
> Transposes a two-dimensional array.

- 使用 `Array.prototype.map()` 创建给定二维数组的转置。

```js
const transpose = arr => arr[0].map((col, i) => arr.map(row => row[i]));
```

```js
transpose([[1, 2, 3], [4, 5, 6], [7, 8, 9], [10, 11, 12]]);
// [[1, 4, 7, 10], [2, 5, 8, 11], [3, 6, 9, 12]
```
