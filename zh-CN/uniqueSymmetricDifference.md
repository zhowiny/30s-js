---
title: 数组唯一对称差(Array unique symmetric difference)
tags: array,math
expertise: intermediate
cover: blog_images/paper-card.jpg
firstSeen: 2018-08-17T08:37:08+03:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

# 返回两个数组之间的唯一对称差，不包含来自任一数组的重复值。
> Returns the unique symmetric difference between two arrays, not containing duplicate values from either array.

- 在每个数组上使用 `Array.prototype.filter()` 和 `Array.prototype.includes()` 来删除另一个数组中包含的值。
- 从结果中创建一个 `Set` ，删除重复值。

```js
const uniqueSymmetricDifference = (a, b) => [
  ...new Set([
    ...a.filter(v => !b.includes(v)),
    ...b.filter(v => !a.includes(v)),
  ]),
];
```

```js
uniqueSymmetricDifference([1, 2, 3], [1, 2, 4]); // [3, 4]
uniqueSymmetricDifference([1, 2, 2], [1, 3, 1]); // [2, 3]
```
