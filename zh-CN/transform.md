---
title: 变换对象(Transform object)
tags: object
expertise: intermediate
cover: blog_images/fishermen.jpg
firstSeen: 2018-01-12T13:55:49+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

# 对累加器和对象中的每个键应用函数（从左到右）。
> Applies a function against an accumulator and each key in the object (from left to right).

- 使用 `Object.keys()` 迭代对象中的每个键。
- 使用 `Array.prototype.reduce()` 对给定的累加器应用指定的函数。

```js
const transform = (obj, fn, acc) =>
  Object.keys(obj).reduce((a, k) => fn(a, obj[k], k, obj), acc);
```

```js
transform(
  { a: 1, b: 2, c: 1 },
  (r, v, k) => {
    (r[v] || (r[v] = [])).push(k);
    return r;
  },
  {}
); // { '1': ['a', 'c'], '2': ['b'] }
```
