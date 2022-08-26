---
title: 检查所有数组元素是否唯一(Check if all array elements are unique)
tags: array
expertise: beginner
cover: blog_images/jars-on-shelf.jpg
firstSeen: 2020-10-19T19:47:26+03:00
lastUpdated: 2021-01-08T00:23:44+02:00
---

### 检查数组中的所有元素是否唯一。
> Checks if all elements in an array are unique.

- 从映射的值创建一个新的“Set”，以仅保留唯一的出现。
- 使用 `Array.prototype.length` 和 `Set.prototype.size` 将唯一值的长度与原始数组进行比较。
-
```js
const allUnique = arr => arr.length === new Set(arr).size;
```

```js
allUnique([1, 2, 3, 4]); // true
allUnique([1, 1, 2, 3]); // false
```
