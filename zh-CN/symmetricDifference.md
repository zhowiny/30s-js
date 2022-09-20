---
title: 数组对称差(Array symmetric difference)
tags: array,math
expertise: intermediate
cover: blog_images/trippy-chemicals.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 返回两个数组之间的对称差异，而不过滤掉重复值。
> Returns the symmetric difference between two arrays, without filtering out duplicate values.

- 从每个数组中创建一个`Set`，以获取每个数组的唯一值。
- 在它们中的每一个上使用 `Array.prototype.filter()` 以仅保留不包含在另一个中的值。

```js
const symmetricDifference = (a, b) => {
  const sA = new Set(a),
    sB = new Set(b);
  return [...a.filter(x => !sB.has(x)), ...b.filter(x => !sA.has(x))];
};
```

```js
symmetricDifference([1, 2, 3], [1, 2, 4]); // [3, 4]
symmetricDifference([1, 2, 2], [1, 3, 1]); // [2, 2, 3]
```
