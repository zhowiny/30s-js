---
title: 归并排序(Merge sort)
tags: algorithm,array,recursion
expertise: advanced
author: maciv
cover: blog_images/baloons-field.jpg
firstSeen: 2020-12-27T22:44:32+02:00
lastUpdated: 2020-12-27T22:44:32+02:00
---

### 使用归并排序算法对数字数组进行排序。
> Sorts an array of numbers, using the merge sort algorithm.

- 使用递归。
- 如果数组的 `length` 小于 `2`，则返回数组。
- 使用 `Math.floor()` 计算数组的中点。
- 使用 `Array.prototype.slice()` 将数组一分为二，并在创建的子数组上递归调用 `mergeSort()`。
- 最后，使用 `Array.from()` 和 `Array.prototype.shift()` 将两个排序后的子数组合并为一个。

```js
const mergeSort = arr => {
  if (arr.length < 2) return arr;
  const mid = Math.floor(arr.length / 2);
  const l = mergeSort(arr.slice(0, mid));
  const r = mergeSort(arr.slice(mid, arr.length));
  return Array.from({ length: l.length + r.length }, () => {
    if (!l.length) return r.shift();
    else if (!r.length) return l.shift();
    else return l[0] > r[0] ? r.shift() : l.shift();
  });
};
```

```js
mergeSort([5, 1, 4, 2, 3]); // [1, 2, 3, 4, 5]
```
