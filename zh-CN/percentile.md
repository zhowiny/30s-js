---
title: 计算匹配的百分比(Percentile of matches)
tags: math
expertise: intermediate
cover: blog_images/red-berries.jpg
firstSeen: 2017-12-13T12:50:16+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 计算给定数组中小于或等于给定值的数字的百分比。
> Calculates the percentage of numbers in the given array that are less or equal to the given value.

- 使用 `Array.prototype.reduce()` 计算有多少数字低于该值以及有多少是相同的值并应用百分位数公式。

```js
const percentile = (arr, val) =>
  (100 *
    arr.reduce(
      (acc, v) => acc + (v < val ? 1 : 0) + (v === val ? 0.5 : 0),
      0
    )) /
  arr.length;
```

```js
percentile([1, 2, 3, 4, 5, 6, 7, 8, 9, 10], 6); // 55
```
