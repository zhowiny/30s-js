---
title: 可迭代对象的超集(Superset of iterable)
tags: array
expertise: intermediate
author: maciv
cover: blog_images/waves-from-above-2.jpg
firstSeen: 2020-10-11T11:53:19+03:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 检查第一个可迭代对象是否是第二个可迭代对象的超集，不包括重复值。
> Checks if the first iterable is a superset of the second one, excluding duplicate values.

- 使用 `Set` 构造函数从每个可迭代对象中创建一个新的 `Set` 对象。
- 使用 `Array.prototype.every()` 和 `Set.prototype.has()` 检查第二个可迭代对象中的每个值是否包含在第一个可迭代对象中。

```js
const superSet = (a, b) => {
  const sA = new Set(a), sB = new Set(b);
  return [...sB].every(v => sA.has(v));
};
```

```js
superSet(new Set([1, 2, 3, 4]), new Set([1, 2])); // true
superSet(new Set([1, 2, 3, 4]), new Set([1, 5])); // false
```
