---
title: 根据函数获取数组对称差(Array symmetric difference)
tags: array
expertise: intermediate
cover: blog_images/digital-nomad.jpg
firstSeen: 2018-01-24T11:59:02+02:00
lastUpdated: 2020-10-18T14:58:09+03:00
---

### 使用提供的函数作为比较器，返回两个数组之间的对称差。
> Returns the symmetric difference between two arrays, using a provided function as a comparator.

- 使用 `Array.prototype.filter()` 和 `Array.prototype.findIndex()` 找到合适的值。

```js
const symmetricDifferenceWith = (arr, val, comp) => [
  ...arr.filter(a => val.findIndex(b => comp(a, b)) === -1),
  ...val.filter(a => arr.findIndex(b => comp(a, b)) === -1)
];
```

```js
symmetricDifferenceWith(
  [1, 1.2, 1.5, 3, 0],
  [1.9, 3, 0, 3.9],
  (a, b) => Math.round(a) === Math.round(b)
); // [1, 1.2, 3.9]
```
