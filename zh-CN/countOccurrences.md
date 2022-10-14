---
title: 计算出现次数(Count occurrences)
tags: array
expertise: intermediate
cover: blog_images/dark-leaves-4.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-18T23:04:45+03:00
---

# 计算数组中某个值的出现次数。
> Counts the occurrences of a value in an array.

- 每次在数组中遇到特定值时，使用 `Array.prototype.reduce()` 递增计数器。

```js
const countOccurrences = (arr, val) =>
  arr.reduce((a, v) => (v === val ? a + 1 : a), 0);
```

```js
countOccurrences([1, 1, 2, 1, 2, 3], 1); // 3
```
