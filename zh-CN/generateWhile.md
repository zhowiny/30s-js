---
title: 满足条件时生成值(Generate while condition is met)
tags: function,generator
expertise: advanced
author: chalarangelo
cover: blog_images/lake-loop.jpg
firstSeen: 2022-01-21T05:00:00-04:00
---

# 创建一个生成器，只要满足给定条件，它就会不断生成新值。
> Creates a generator, that keeps producing new values as long as the given condition is met.

- 使用 `seed` 值初始化当前的 `val`。
- 当使用当前 `val` 调用的 `condition` 函数返回 `true` 时，使用 `while` 循环进行迭代。
- 使用 `yield` 返回当前的 `val` 并可选择接收新的种子值 `nextSeed`。
- 使用 `next` 函数从当前 `val` 和 `nextSeed` 计算下一个值。

```js
const generateWhile = function* (seed, condition, next) {
  let val = seed;
  let nextSeed = null;
  while (condition(val)) {
    nextSeed = yield val;
    val = next(val, nextSeed);
  }
  return val;
};
```

```js
[...generateWhile(1, v => v <= 5, v => ++v)]; // [1, 2, 3, 4, 5]
```
