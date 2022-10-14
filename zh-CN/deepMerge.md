---
title: 深度合并对象(Deep merge objects)
tags: object,function
expertise: advanced
author: chalarangelo
cover: blog_images/coffee-drip.jpg
firstSeen: 2021-07-25T05:00:00-04:00
---

# 深度合并两个对象，使用一个函数来处理两者中存在的`keys`。
> Deeply merges two objects, using a function to handle keys present in both.

- 使用 `Object.keys()` 获取两个对象的键，从它们创建一个 `Set` 并使用扩展运算符 (`...`) 创建一个包含所有唯一键的数组。
- 使用 `Array.prototype.reduce()` 将每个唯一键添加到对象，使用 `fn` 组合两个给定对象的值。

```js
const deepMerge = (a, b, fn) =>
  [...new Set([...Object.keys(a), ...Object.keys(b)])].reduce(
    (acc, key) => ({ ...acc, [key]: fn(key, a[key], b[key]) }),
    {}
  );
```

```js
deepMerge(
  { a: true, b: { c: [1, 2, 3] } },
  { a: false, b: { d: [1, 2, 3] } },
  (key, a, b) => (key === 'a' ? a && b : Object.assign({}, a, b))
);
// { a: false, b: { c: [ 1, 2, 3 ], d: [ 1, 2, 3 ] } }

deepMerge(
  { a: true, b: { c: [1, 2, 3] }, x: { foo: { bar: 1,  baz: 3 } } },
  { a: false, b: { c: [4, 5] }, x: { foo: { bar: 2 } } },
  (key, a, b) =>
    typeof a === 'object' || typeof b === 'object'
      ? deepMerge(a ?? {}, b ?? {}, (key, o1, o2) => Object.assign({}, o1, o2))
      : a && b
);
// { a: false, b: { c: [ 4, 5, 3 ] }, x: { foo: {bar: 2, baz: 3 } } }
```
