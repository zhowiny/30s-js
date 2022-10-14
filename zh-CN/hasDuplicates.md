---
title: 检查数组是否有重复(Check if array has duplicates)
tags: array
expertise: beginner
cover: blog_images/umbrellas.jpg
firstSeen: 2020-10-22T20:23:09+03:00
lastUpdated: 2020-10-22T20:23:09+03:00
---

# 检查一维数组中是否存在重复值。
> Checks if there are duplicate values in a flat array.

- 使用 `Set` 获取数组中的唯一值。
- 使用 `Set.prototype.size` 和 `Array.prototype.length` 检查唯一值的计数是否与原始数组中的元素相同。

```js
const hasDuplicates = arr => new Set(arr).size !== arr.length;
```

```js
hasDuplicates([0, 1, 1, 2]); // true
hasDuplicates([0, 1, 2, 3]); // false
```
