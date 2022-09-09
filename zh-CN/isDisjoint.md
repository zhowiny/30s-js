---
title: 可迭代对象是否不相交(Disjointed iterables)
tags: array
expertise: intermediate
author: maciv
cover: blog_images/interior-9.jpg
firstSeen: 2020-10-11T11:53:01+03:00
lastUpdated: 2020-10-11T11:53:01+03:00
---

### 检查两个可迭代对象是否不相交（没有共同值）。
> Checks if the two iterables are disjointed (have no common values).

- 使用 `Set` 构造函数从每个可迭代对象中创建一个新的 `Set` 对象。
- 使用 `Array.prototype.every()` 和 `Set.prototype.has()` 来检查两个可迭代对象没有共同的值。

```js
const isDisjoint = (a, b) => {
  const sA = new Set(a), sB = new Set(b);
  return [...sA].every(v => !sB.has(v));
};
```

```js
isDisjoint(new Set([1, 2]), new Set([3, 4])); // true
isDisjoint(new Set([1, 2]), new Set([1, 3])); // false
```
