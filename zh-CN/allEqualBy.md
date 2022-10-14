---
title: 根据函数检查数组元素是否相等(Check if array elements are equal based on function)
tags: array
expertise: intermediate
author: maciv
cover: blog_images/orange-coffee-2.jpg
firstSeen: 2020-10-19T22:14:49+03:00
lastUpdated: 2020-10-19T22:14:49+03:00
---

# 根据提供的映射函数检查数组中的所有元素是否相等。
> Checks if all elements in an array are equal, based on the provided mapping function.

- 将 `fn` 应用于 `arr` 的第一个元素。
- 使用 `Array.prototype.every()` 检查 `fn` 是否为数组中的所有元素返回与第一个元素相同的值。
- 数组中的元素使用严格比较运算符进行比较，不考虑 `NaN` 自不等式。

```js
const allEqualBy = (arr, fn) => {
  const eql = fn(arr[0]);
  return arr.every(val => fn(val) === eql);
};
```

```js
allEqualBy([1.1, 1.2, 1.3], Math.round); // true
allEqualBy([1.1, 1.3, 1.6], Math.round); // false
```
