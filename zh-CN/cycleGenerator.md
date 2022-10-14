---
title: 环形生成器(Cycle generator)
tags: function,generator
expertise: advanced
author: chalarangelo
cover: blog_images/secret-tree.jpg
firstSeen: 2020-10-11T17:05:38+03:00
lastUpdated: 2020-10-11T17:05:38+03:00
---

# 创建一个生成器，无限期地循环给定数组。
> Creates a generator, looping over the given array indefinitely.

- 使用非终止的 `while` 循环，每次调用 `Generator.prototype.next()` 时都会产生一个值。
- 使用带有 `Array.prototype.length` 的模块运算符 (`%`) 来获取下一个值的索引，并在每个 `yield` 语句之后递增计数器。

```js
const cycleGenerator = function* (arr) {
  let i = 0;
  while (true) {
    yield arr[i % arr.length];
    i++;
  }
};
```

```js
const binaryCycle = cycleGenerator([0, 1]);
binaryCycle.next(); // { value: 0, done: false }
binaryCycle.next(); // { value: 1, done: false }
binaryCycle.next(); // { value: 0, done: false }
binaryCycle.next(); // { value: 1, done: false }
```
