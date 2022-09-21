---
title: 数组的乘集(Cross product of arrays)
tags: array,math
expertise: intermediate
cover: blog_images/cup-of-orange.jpg
firstSeen: 2018-01-24T15:55:03+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

### 通过从数组创建每个可能的对，从提供的两个数组中创建一个新数组。
> Creates a new array out of the two supplied by creating each possible pair from the arrays.

- 使用 `Array.prototype.reduce()`、`Array.prototype.map()` 和 `Array.prototype.concat()` 从两个数组的元素中生成每个可能的对。

```js
const xProd = (a, b) =>
  a.reduce((acc, x) => acc.concat(b.map(y => [x, y])), []);
```

```js
xProd([1, 2], ['a', 'b']); // [[1, 'a'], [1, 'b'], [2, 'a'], [2, 'b']]
```
