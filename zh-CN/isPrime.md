---
title: 数是质数(素数)(Number is prime)
tags: math,algorithm
expertise: beginner
cover: blog_images/thread.jpg
firstSeen: 2017-12-19T22:35:56+02:00
lastUpdated: 2021-01-12T19:36:36+02:00
---

# 检查提供的整数是否为素数。
> Checks if the provided integer is a prime number.

- 检查从 `2` 到给定数字的平方根的数字。
- 如果其中任何一个除以给定的数字，则返回 `false`，否则返回 `true`，除非数字小于 `2`。

```js
const isPrime = num => {
  const boundary = Math.floor(Math.sqrt(num));
  for (let i = 2; i <= boundary; i++) if (num % i === 0) return false;
  return num >= 2;
};
```

```js
isPrime(11); // true
```
