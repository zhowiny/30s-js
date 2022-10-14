---
title: 数组交集(Array intersection)
tags: array
expertise: intermediate
cover: blog_images/red-berries.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 返回两个数组中都存在的元素，过滤重复值。
> Returns the elements that exist in both arrays, filtering duplicate values.

- 从 `b` 创建一个 `Set`，然后在 `a` 上使用 `Array.prototype.filter()` 以仅保留 `b` 中包含的值。

```js
const intersection = (a, b) => {
  const s = new Set(b);
  return [...new Set(a)].filter(x => s.has(x));
};
```

```js
intersection([1, 2, 3], [4, 3, 2]); // [2, 3]
```
