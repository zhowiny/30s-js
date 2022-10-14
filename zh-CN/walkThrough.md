---
title: 通过生成器遍历对象所有键(Walk through object)
tags: object,recursion,generator
expertise: advanced
author: chalarangelo
cover: blog_images/bridge.jpg
firstSeen: 2020-12-31T13:03:15+02:00
lastUpdated: 2021-11-15T13:18:18+02:00
---

# 创建一个生成器，它遍历给定对象的所有键。
> Creates a generator, that walks through all the keys of a given object.

- 使用递归。
- 定义一个生成器函数 `walk`，它接受一个对象和一个键数组。
- 使用 `for...of` 循环和 `Object.keys()` 来迭代对象的键。
- 使用 `typeof` 检查给定对象中的每个值本身是否是一个对象。
- 如果是这样，使用 `yield*` 表达式递归地委托给相同的生成器函数，`walk`，将当前的 `key` 附加到键数组中。 否则，`yield` 表示当前路径的键数组和给定 `key` 的值。
- 使用 `yield*` 表达式委托给 `walk` 生成器函数。

```js
const walkThrough = function* (obj) {
  const walk = function* (x, previous = []) {
    for (let key of Object.keys(x)) {
      if (typeof x[key] === 'object') yield* walk(x[key], [...previous, key]);
      else yield [[...previous, key], x[key]];
    }
  };
  yield* walk(obj);
};
```

```js
const obj = {
  a: 10,
  b: 20,
  c: {
    d: 10,
    e: 20,
    f: [30, 40]
  },
  g: [
    {
      h: 10,
      i: 20
    },
    {
      j: 30
    },
    40
  ]
};
[...walkThrough(obj)];
/*
[
  [['a'], 10],
  [['b'], 20],
  [['c', 'd'], 10],
  [['c', 'e'], 20],
  [['c', 'f', '0'], 30],
  [['c', 'f', '1'], 40],
  [['g', '0', 'h'], 10],
  [['g', '0', 'i'], 20],
  [['g', '1', 'j'], 30],
  [['g', '2'], 40]
]
*/
```
