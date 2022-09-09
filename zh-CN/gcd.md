---
title: 最大公约数(Greatest common divisor)
tags: math,algorithm,recursion
expertise: intermediate
cover: blog_images/flower-pond.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-12-29T12:36:50+02:00
---

### 计算两个或多个数字/数组之间的最大公约数。
> Calculates the greatest common divisor between two or more numbers/arrays.

- 内部 `_gcd` 函数使用递归。
- 基本情况是 `y` 等于 `0`。 在这种情况下，返回 `x`。
- 否则，返回 `y` 的 GCD 和除法的余数 `x / y`。

```js
const gcd = (...arr) => {
  const _gcd = (x, y) => (!y ? x : gcd(y, x % y));
  return [...arr].reduce((a, b) => _gcd(a, b));
};
```

```js
gcd(8, 36); // 4
gcd(...[12, 8, 32]); // 4
```
