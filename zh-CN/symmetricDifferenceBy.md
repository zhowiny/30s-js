---
title: 映射数组对称差(Mapped array symmetric difference)
tags: array
expertise: intermediate
cover: blog_images/river-houses.jpg
firstSeen: 2018-01-24T11:59:02+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 在将提供的函数应用于两个数组的每个数组元素后，返回两个数组之间的对称差。
> Returns the symmetric difference between two arrays, after applying the provided function to each array element of both.

- 从每个数组中创建一个 `Set` 以在对它们应用 `fn` 后获取每个数组的唯一值。
- 在它们中的每一个上使用 `Array.prototype.filter()` 以仅保留不包含在另一个中的值。

```js
const symmetricDifferenceBy = (a, b, fn) => {
  const sA = new Set(a.map(v => fn(v))),
    sB = new Set(b.map(v => fn(v)));
  return [...a.filter(x => !sB.has(fn(x))), ...b.filter(x => !sA.has(fn(x)))];
};
```

```js
symmetricDifferenceBy([2.1, 1.2], [2.3, 3.4], Math.floor); // [ 1.2, 3.4 ]
symmetricDifferenceBy(
  [{ id: 1 }, { id: 2 }, { id: 3 }],
  [{ id: 1 }, { id: 2 }, { id: 4 }],
  i => i.id
);
// [{ id: 3 }, { id: 4 }]
```
