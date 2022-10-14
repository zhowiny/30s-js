---
title: 检查数组是否包含任何值(Check if array includes any values)
tags: array
expertise: beginner
cover: blog_images/book-stopper.jpg
firstSeen: 2019-11-03T23:49:17+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 检查数组是否包含任何值
> Checks if at least one element of `values` is included in `arr`.

- 使用 `Array.prototype.some()` 和 `Array.prototype.includes()` 检查 `values` 的至少一个元素是否包含在 `arr` 中。

```js
const includesAny = (arr, values) => values.some(v => arr.includes(v));
```

```js
includesAny([1, 2, 3, 4], [2, 9]); // true
includesAny([1, 2, 3, 4], [8, 9]); // false
```
