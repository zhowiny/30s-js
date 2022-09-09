---
title: 通过函数获取数组交集(Array intersection based on function)
tags: array
expertise: intermediate
cover: blog_images/cobbled-street.jpg
firstSeen: 2018-01-24T12:53:18+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 在将提供的函数应用于两者的每个数组元素后，返回两个数组中存在的元素。
> Returns the elements that exist in both arrays, after applying the provided function to each array element of both.

- 通过将 `fn` 应用于 `b` 中的所有元素来创建一个 `Set`。
- 在 `a` 上使用 `Array.prototype.filter()` 仅保留元素，当将 `fn` 应用于它们时，这些元素会产生 `b` 中包含的值。

```js
const intersectionBy = (a, b, fn) => {
  const s = new Set(b.map(fn));
  return [...new Set(a)].filter(x => s.has(fn(x)));
};
```

```js
intersectionBy([2.1, 1.2], [2.3, 3.4], Math.floor); // [2.1]
intersectionBy(
  [{ title: 'Apple' }, { title: 'Orange' }],
  [{ title: 'Orange' }, { title: 'Melon' }],
  x => x.title
); // [{ title: 'Orange' }]
```
