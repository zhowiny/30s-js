---
title: 根据函数获取数组并集(Array union based on function)
tags: array
expertise: intermediate
cover: blog_images/orange-coffee-4.jpg
firstSeen: 2018-01-24T12:19:41+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

# 使用提供的比较器函数至少返回一次存在于两个数组中的任何一个中的每个元素。
> Returns every element that exists in any of the two arrays at least once, using a provided comparator function.

- 使用 `Array.prototype.findIndex()` 创建一个 `Set`，其中包含 `a` 的所有值和 `b` 中的值，比较器在 `a` 中找不到匹配项。

```js
const unionWith = (a, b, comp) =>
  Array.from(
    new Set([...a, ...b.filter(x => a.findIndex(y => comp(x, y)) === -1)])
  );
```

```js
unionWith(
  [1, 1.2, 1.5, 3, 0],
  [1.9, 3, 0, 3.9],
  (a, b) => Math.round(a) === Math.round(b)
);
// [1, 1.2, 1.5, 3, 0, 3.9]
```
