---
title: 数字是二的幂(Number is power of two)
tags: math
expertise: beginner
author: chalarangelo
cover: blog_images/flower-portrait-10.jpg
firstSeen: 2019-12-31T13:17:12+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 检查给定数字是否是 `2` 的幂。
> Checks if the given number is a power of `2`.

- 使用按位二进制 AND 运算符 (`&`) 确定 `n` 是否是 `2` 的幂。
- 此外，检查 `n` 是否不假。

```js
const isPowerOfTwo = n => !!n && (n & (n - 1)) == 0;
```

```js
isPowerOfTwo(0); // false
isPowerOfTwo(1); // true
isPowerOfTwo(8); // true
```
