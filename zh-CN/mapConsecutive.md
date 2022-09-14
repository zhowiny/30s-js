---
title: 映射连续元素(Map consecutive elements)
tags: array
expertise: intermediate
author: chalarangelo
cover: blog_images/cold-mountains.jpg
firstSeen: 2021-08-08T05:00:00-04:00
---

### 使用给定函数 `fn` 映射每个 `n` 个连续元素块。
> Maps each block of `n` consecutive elements using the given function, `fn`.

- 使用 `Array.prototype.slice()` 来获取 `arr`，并从左侧删除 `n` 个元素。
- 使用 `Array.prototype.map()` 和 `Array.prototype.slice()` 将 `fn` 应用于 `arr` 中的每个 `n` 连续元素块。

```js
const mapConsecutive = (arr, n, fn) =>
  arr.slice(n - 1).map((v, i) => fn(arr.slice(i, i + n)));
```

```js
mapConsecutive([1, 2, 3, 4, 5, 6, 7, 8, 9, 10], 3, x => x.join('-'));
// ['1-2-3', '2-3-4', '3-4-5', '4-5-6', '5-6-7', '6-7-8', '7-8-9', '8-9-10'];
```
