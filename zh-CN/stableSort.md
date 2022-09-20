---
title: 稳定排序(Stable sort)
tags: array
expertise: advanced
cover: blog_images/horse-sunset.jpg
firstSeen: 2018-02-06T18:33:49+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 对数组进行稳定排序，当它们的值相同时保留目标的初始索引。
> Performs stable sorting of an array, preserving the initial indexes of items when their values are the same.

- 使用 `Array.prototype.map()` 将输入数组的每个元素与其对应的索引配对。
- 使用 `Array.prototype.sort()` 和 `compare` 函数对列表进行排序，如果比较的目标相等，则保留它们的初始顺序。
- 使用 `Array.prototype.map()` 转换回初始数组项。
- 不改变原始数组，而是返回一个新数组。

```js
const stableSort = (arr, compare) =>
  arr
    .map((item, index) => ({ item, index }))
    .sort((a, b) => compare(a.item, b.item) || a.index - b.index)
    .map(({ item }) => item);
```

```js
const arr = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const stable = stableSort(arr, () => 0); // [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```
