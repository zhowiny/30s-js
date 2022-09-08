---
title: 斐波那契数列(Fibonacci)
tags: math,algorithm
expertise: intermediate
cover: blog_images/highlands.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-12-28T13:49:24+02:00
---

### 生成一个数组，包含斐波那契数列，直到第 n 项。
> Generates an array, containing the Fibonacci sequence, up until the nth term.

- 使用 `Array.from()` 创建一个特定长度的空数组，初始化前两个值（`0` 和 `1`）。
- 使用 `Array.prototype.reduce()` 和 `Array.prototype.concat()` 将值添加到数组中，使用最后两个值的总和，前两个值除外。

```js
const fibonacci = n =>
  Array.from({ length: n }).reduce(
    (acc, val, i) => acc.concat(i > 1 ? acc[i - 1] + acc[i - 2] : i),
    []
  );
```

```js
fibonacci(6); // [0, 1, 1, 2, 3, 5]
```
