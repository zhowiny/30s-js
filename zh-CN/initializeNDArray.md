---
title: 初始化 n 维数组(Initialize n-dimensional array)
tags: array,recursion
expertise: intermediate
cover: blog_images/colorful-pots.jpg
firstSeen: 2018-04-14T10:52:39+03:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 创建具有给定值的 n 维数组。
> Create a n-dimensional array with given value.

- 使用递归。
- 使用 `Array.from()`、`Array.prototype.map()` 生成行，其中每个行都是使用 `initializeNDArray()` 初始化的新数组。

```js
const initializeNDArray = (val, ...args) =>
  args.length === 0
    ? val
    : Array.from({ length: args[0] }).map(() =>
        initializeNDArray(val, ...args.slice(1))
      );
```

```js
initializeNDArray(1, 3); // [1, 1, 1]
initializeNDArray(5, 2, 2, 2); // [[[5, 5], [5, 5]], [[5, 5], [5, 5]]]
```
