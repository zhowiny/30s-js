---
title: 数字是十的幂(Number is power of ten)
tags: math
expertise: beginner
author: chalarangelo
cover: blog_images/boulder-beach.jpg
firstSeen: 2021-01-06T22:53:58+02:00
lastUpdated: 2021-01-06T22:53:58+02:00
---

# 检查给定数字是否是 `10` 的幂。
> Checks if the given number is a power of `10`.

- 使用 `Math.log10()` 和模运算符 (`%`) 来确定 `n` 是否是 `10` 的幂。

```js
const isPowerOfTen = n => Math.log10(n) % 1 === 0;
```

```js
isPowerOfTen(1); // true
isPowerOfTen(10); // true
isPowerOfTen(20); // false
```
