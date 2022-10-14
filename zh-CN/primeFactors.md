---
title: 数的质因数(Prime factors of number)
tags: math,algorithm
expertise: beginner
author: maciv
cover: blog_images/dark-leaves-3.jpg
firstSeen: 2020-12-28T13:11:01+02:00
lastUpdated: 2020-12-28T13:11:01+02:00
---

# 使用试除法算法找到给定数的质因数。
> Finds the prime factors of a given number using the trial division algorithm.

- 使用 `while` 循环遍历所有可能的素因数，从 `2` 开始。
- 如果当前因子 `f` 正好整除 `n`，则将 `f` 添加到因子数组中，然后将 `n` 除以 `f`。 否则，将 `f` 加1。

```js
const primeFactors = n => {
  let a = [],
    f = 2;
  while (n > 1) {
    if (n % f === 0) {
      a.push(f);
      n /= f;
    } else {
      f++;
    }
  }
  return a;
};
```

```js
primeFactors(147); // [3, 7, 7]
```
