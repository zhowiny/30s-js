---
title: 映射数组并集(Mapped array union)
tags: array
expertise: intermediate
cover: blog_images/lake-church.jpg
firstSeen: 2018-01-24T12:19:41+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

### 在将提供的函数应用于两者的每个数组元素之后，至少返回一次存在于两个数组中的任何一个中的每个元素。
> Returns every element that exists in any of the two arrays at least once, after applying the provided function to each array element of both.

- 通过将所有`fn`应用于`a`的所有值来创建一个`Set`。
- 从 `a` 和 `b` 中的所有元素创建一个 `Set`，其值在应用 `fn` 后与先前创建的集合中的值不匹配。
- 返回转换为数组的最后一组。

```js
const unionBy = (a, b, fn) => {
  const s = new Set(a.map(fn));
  return Array.from(new Set([...a, ...b.filter(x => !s.has(fn(x)))]));
};
```

```js
unionBy([2.1], [1.2, 2.3], Math.floor); // [2.1, 1.2]
unionBy([{ id: 1 }, { id: 2 }], [{ id: 2 }, { id: 3 }], x => x.id)
// [{ id: 1 }, { id: 2 }, { id: 3 }]
```
