---
title: 二分搜索|二分查找(Binary search)
tags: algorithm,array
expertise: beginner
author: chalarangelo
cover: blog_images/zen-indoors.jpg
firstSeen: 2020-12-28T12:35:44+02:00
lastUpdated: 2020-12-29T13:06:47+02:00
---

# 使用二分搜索算法在已排序数组中查找给定元素的索引。
> Finds the index of a given element in a sorted array using the binary search algorithm.

- 声明左右搜索边界`l`和`r`，分别初始化为`0`和数组的`length`。
- 使用 `while` 循环重复缩小搜索子数组，使用 `Math.floor()` 将其切成两半。
- 如果找到，则返回元素的索引，否则返回 `-1`。
- **注意：** 不考虑数组中的重复值。

```js
const binarySearch = (arr, item) => {
  let l = 0,
    r = arr.length - 1;
  while (l <= r) {
    const mid = Math.floor((l + r) / 2);
    const guess = arr[mid];
    if (guess === item) return mid;
    if (guess > item) r = mid - 1;
    else l = mid + 1;
  }
  return -1;
};
```

```js
binarySearch([1, 2, 3, 4, 5], 1); // 0
binarySearch([1, 2, 3, 4, 5], 5); // 4
binarySearch([1, 2, 3, 4, 5], 6); // -1
```
