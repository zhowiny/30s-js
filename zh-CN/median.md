---
title: 中位数(Median)
tags: math,array
expertise: intermediate
cover: blog_images/old-consoles.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 计算数字数组的中位数。
> Calculates the median of an array of numbers.

- 找到数组的中间，使用 `Array.prototype.sort()` 对值进行排序。
- 如果 `Array.prototype.length` 为奇数，则返回中点的数字，否则返回中间两个数字的平均值。

```js
const median = arr => {
  const mid = Math.floor(arr.length / 2),
    nums = [...arr].sort((a, b) => a - b);
  return arr.length % 2 !== 0 ? nums[mid] : (nums[mid - 1] + nums[mid]) / 2;
};
```

```js
median([5, 6, 50, 1, -5]); // 5
```
