---
title: 数的N次方根(Nth root of number)
tags: math
expertise: beginner
author: chalarangelo
cover: blog_images/tree-roots.jpg
firstSeen: 2021-01-06T22:47:48+02:00
lastUpdated: 2021-01-06T22:47:48+02:00
---

### 计算给定数字的N次方根。
> Calculates the nth root of a given number.

- 使用 `Math.pow()` 计算 `x` 的 `1 / n` 次方，等于 `x`的 `n` 次方根。

```js
const nthRoot = (x, n) => Math.pow(x, 1 / n);
```

```js
nthRoot(32, 5); // 2
```
