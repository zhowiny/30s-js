---
title: 根据函数检查所有数组元素是否唯一(Check if all array elements are unique based on function)
tags: array
expertise: intermediate
author: maciv
cover: blog_images/digital-nomad-10.jpg
firstSeen: 2020-10-19T22:15:05+03:00
lastUpdated: 2021-01-08T00:23:44+02:00
---

### 根据提供的映射函数检查数组中的所有元素是否唯一。
> Checks if all elements in an array are unique, based on the provided mapping function.

- 使用 `Array.prototype.map()` 将 `fn` 应用于 `arr` 中的所有元素。
- 从映射的值创建一个新的“Set”，以仅保留唯一的出现。
- 使用 `Array.prototype.length` 和 `Set.prototype.size` 将唯一映射值的长度与原始数组进行比较。

```js
const allUniqueBy = (arr, fn) => arr.length === new Set(arr.map(fn)).size;
```

```js
allUniqueBy([1.2, 2.4, 2.9], Math.round); // true
allUniqueBy([1.2, 2.3, 2.4], Math.round); // false
```
