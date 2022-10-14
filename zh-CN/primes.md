---
title: 在指定的数字范围内取质数(Primes up to given number)
tags: math,algorithm
expertise: intermediate
cover: blog_images/apples.jpg
firstSeen: 2017-12-21T12:20:22+02:00
lastUpdated: 2020-12-28T13:49:24+02:00
---

# 使用[埃拉托色尼筛](https://zh.wikipedia.org/zh-cn/%E5%9F%83%E6%8B%89%E6%89%98%E6%96%AF%E7%89%B9%E5%B0%BC%E7%AD%9B%E6%B3%95)法生成给定数量的素数。
> Generates primes up to a given number, using the Sieve of Eratosthenes.

- Generate an array from `2` to the given number.
- Use `Array.prototype.filter()` to filter out the values divisible by any number from `2` to the square root of the provided number.

```js
const primes = num => {
  let arr = Array.from({ length: num - 1 }).map((x, i) => i + 2),
    sqroot = Math.floor(Math.sqrt(num)),
    numsTillSqroot = Array.from({ length: sqroot - 1 }).map((x, i) => i + 2);
  numsTillSqroot.forEach(x => (arr = arr.filter(y => y % x !== 0 || y === x)));
  return arr;
};
```

```js
primes(10); // [2, 3, 5, 7]
```
