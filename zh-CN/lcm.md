---
title: 最小公倍数(Least common multiple)
tags: math,algorithm,recursion
expertise: intermediate
cover: blog_images/waving-over-lake.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-12-28T13:49:24+02:00
---

# 计算两个或多个数字的最小公倍数。
> Calculates the least common multiple of two or more numbers.

- 使用最大公约数 (GCD) 公式和 `lcm(x, y) = x * y / gcd(x, y)` 来确定最小公倍数。
- GCD 公式使用递归。

```js
const lcm = (...arr) => {
  const gcd = (x, y) => (!y ? x : gcd(y, x % y));
  const _lcm = (x, y) => (x * y) / gcd(x, y);
  return [...arr].reduce((a, b) => _lcm(a, b));
};
```

```js
lcm(12, 7); // 84
lcm(...[1, 3, 4, 5]); // 60
```
