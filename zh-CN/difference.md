---
title: 数组的差异(Array difference)
tags: array
expertise: beginner
cover: blog_images/interior-3.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-10-19T18:51:03+03:00
---

### 计算两个数组之间的差异，而不过滤重复值。
> Calculates the difference between two arrays, without filtering duplicate values.

- 从 `b` 创建一个 `Set` 以获取 `b` 中的唯一值。
- 在 `a` 上使用 `Array.prototype.filter()` 以仅保留 `b` 中不包含的值，使用 `Set.prototype.has()`。

```js
const difference = (a, b) => {
  const s = new Set(b);
  return a.filter(x => !s.has(x));
};
```

```js
difference([1, 2, 3, 3], [1, 2, 4]); // [3, 3]
```
