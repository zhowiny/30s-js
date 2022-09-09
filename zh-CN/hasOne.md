---
title: 检查数组是否只有一个匹配项(Check if array has only one match)
tags: array
expertise: beginner
author: chalarangelo
cover: blog_images/interior-10.jpg
firstSeen: 2021-07-04T05:00:00-04:00
---

### 检查数组是否只有一个与给定函数匹配的值。
> Checks if an array has only one value matching the given function.

- 结合使用 `Array.prototype.filter()` 和 `fn` 来查找所有匹配的数组元素。
- 使用 `Array.prototype.length` 检查是否只有一个元素匹配 `fn`。

```js
const hasOne = (arr, fn) => arr.filter(fn).length === 1;
```

```js
hasOne([1, 2], x => x % 2); // true
hasOne([1, 3], x => x % 2); // false
```
