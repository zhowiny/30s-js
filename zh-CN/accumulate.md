---
title: 数组部分和(Partial sum array)
tags: math,array
expertise: intermediate
author: chalarangelo
cover: blog_images/river-house-lights.jpg
firstSeen: 2020-05-04T12:20:46+03:00
lastUpdated: 2022-01-30T13:10:13+02:00
---

### 创建一个部分和数组
> Creates an array of partial sums.

- 使用 `Array.prototype.reduce()`, 用空数组初始化累加器, 迭代 `nums`。
- 使用 `Array.prototype.slice()` 获取先前的部分总和或 `0`, 并将当前元素添加到其中。
- 使用扩展运算符 (`...`) 将新的部分总和添加到包含先前总和的累加器数组中。

```js
const accumulate = (...nums) =>
  nums.reduce((acc, n) => [...acc, n + (acc.slice(-1)[0] || 0)], []);
```

```js
accumulate(1, 2, 3, 4); // [1, 3, 6, 10]
accumulate(...[1, 2, 3, 4]); // [1, 3, 6, 10]
```
