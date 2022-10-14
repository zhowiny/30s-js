---
title: 检查数组元素是否相等(Check if array elements are equal)
tags: array
expertise: beginner
cover: blog_images/shelf-plant.jpg
firstSeen: 2018-08-03T00:03:08+03:00
lastUpdated: 2020-10-18T20:24:28+03:00
---

# 检查数组中的所有元素是否相等。
> Checks if all elements in an array are equal.

- 使用 `Array.prototype.every()` 检查数组的所有元素是否与第一个元素相同。
- 数组中的元素使用严格比较运算符进行比较，不考虑 `NaN` 自不等式。

```js
const allEqual = arr => arr.every(val => val === arr[0]);
```

```js
allEqual([1, 2, 3, 4, 5, 6]); // false
allEqual([1, 1, 1, 1]); // true
```
