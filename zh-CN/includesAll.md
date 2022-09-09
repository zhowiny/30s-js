---
title: 检查数组是否包含所有值(Check if array includes all values)
tags: array
expertise: beginner
cover: blog_images/tomatoes.jpg
firstSeen: 2019-11-04T21:37:16+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 检查 `values` 中的所有元素是否包含在 `arr` 中。
> Checks if all the elements in `values` are included in `arr`.

- 使用 `Array.prototype.every()` 和 `Array.prototype.includes()` 检查 `values` 的所有元素是否包含在 `arr` 中。

```js
const includesAll = (arr, values) => values.every(v => arr.includes(v));
```

```js
includesAll([1, 2, 3, 4], [1, 4]); // true
includesAll([1, 2, 3, 4], [1, 5]); // false
```
