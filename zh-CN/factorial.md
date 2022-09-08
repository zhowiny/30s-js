---
title: 数的阶乘(Factorial of number)
tags: math,algorithm,recursion
expertise: beginner
cover: blog_images/flower-vase.jpg
firstSeen: 2017-12-07T14:41:33+02:00
lastUpdated: 2020-12-28T13:49:24+02:00
---

### 计算一个数的阶乘。
> Calculates the factorial of a number.

- 使用递归。
- 如果 `n` 小于或等于 `1`，则返回 `1`。
- 否则，返回 `n` 的乘积和 `n - 1` 的阶乘。
- 如果 `n` 是负数，则抛出 `TypeError`。

```js
const factorial = n =>
  n < 0
    ? (() => {
        throw new TypeError('Negative numbers are not allowed!');
      })()
    : n <= 1
    ? 1
    : n * factorial(n - 1);
```

```js
factorial(6); // 720
```
