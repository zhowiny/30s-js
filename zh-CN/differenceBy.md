---
title: 映射数组差异(Mapped array difference)
tags: array
expertise: intermediate
cover: blog_images/keyboard.jpg
firstSeen: 2018-01-24T11:49:03+02:00
lastUpdated: 2020-10-19T18:52:00+03:00
---

### 在将提供的函数应用于两个数组的每个数组元素后，返回两个数组之间的差异。
> Returns the difference between two arrays, after applying the provided function to each array element of both.

- 通过将 `fn` 应用于 `b` 中的每个元素来创建一个 `Set`。
- 使用 `Array.prototype.map()` 将 `fn` 应用于 `a` 中的每个元素。
- 将 `Array.prototype.filter()` 与 `a` 上的 `fn` 结合使用，使用 `Set.prototype.has()` 仅保留 `b` 中未包含的值。

```js
const differenceBy = (a, b, fn) => {
  const s = new Set(b.map(fn));
  return a.map(fn).filter(el => !s.has(el));
};
```

```js
differenceBy([2.1, 1.2], [2.3, 3.4], Math.floor); // [1]
differenceBy([{ x: 2 }, { x: 1 }], [{ x: 1 }], v => v.x); // [2]
```
