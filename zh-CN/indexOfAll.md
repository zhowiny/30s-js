---
title: 所有匹配的的索引(Index of all matches)
tags: array
expertise: intermediate
cover: blog_images/jars-on-shelf-2.jpg
firstSeen: 2018-01-06T12:07:56+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 在数组中查找 `val` 的所有索引。如果 `val` 从未出现，则返回一个空数组。
> Finds all indexes of `val` in an array.
> If `val` never occurs, returns an empty array.

- 使用 `Array.prototype.reduce()` 循环遍历元素并存储匹配元素的索引。

```js
const indexOfAll = (arr, val) =>
  arr.reduce((acc, el, i) => (el === val ? [...acc, i] : acc), []);
```

```js
indexOfAll([1, 2, 3, 1, 2, 3], 1); // [0, 3]
indexOfAll([1, 2, 3], 4); // []
```
