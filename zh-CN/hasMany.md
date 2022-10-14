---
title: 检查数组是否有很多匹配项(Check if array has many matches)
tags: array
expertise: beginner
author: chalarangelo
cover: blog_images/interior-2.jpg
firstSeen: 2021-07-11T05:00:00-04:00
---

# 检查数组是否有多个与给定函数匹配的值。
> Checks if an array has more than one value matching the given function.

- 结合使用 `Array.prototype.filter()` 和 `fn` 来查找所有匹配的数组元素。
- 使用 `Array.prototype.length` 来检查是否有多个元素匹配 `fn`。

```js
const hasMany = (arr, fn) => arr.filter(fn).length > 1;
```

```js
hasMany([1, 3], x => x % 2); // true
hasMany([1, 2], x => x % 2); // false
```
