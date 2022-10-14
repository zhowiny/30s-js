---
title: 等差数列(Arithmetic progression)
tags: math,algorithm
expertise: beginner
author: maciv
cover: blog_images/u-got-this.jpg
firstSeen: 2020-10-04T11:37:07+03:00
lastUpdated: 2021-10-13T19:29:39+02:00
---

# 在等差数列中创建一个数字数组，从给定的正整数开始，直到指定的限制。
> Creates an array of numbers in the arithmetic progression, starting with the given positive integer and up to the specified limit.

- 使用 `Array.from()` 创建所需长度的数组，`lim / n`。 使用 map 函数在给定范围内填充所需的值。

```js
const arithmeticProgression  = (n, lim) =>
  Array.from({ length: Math.ceil(lim / n) }, (_, i) => (i + 1) * n );
```

```js
arithmeticProgression(5, 25); // [5, 10, 15, 20, 25]
```
