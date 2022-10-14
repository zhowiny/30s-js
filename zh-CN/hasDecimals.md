---
title: 数字有小数(Number has decimal digits)
tags: math
expertise: beginner
author: chalarangelo
cover: blog_images/man-cup-laptop.jpg
firstSeen: 2022-05-13T05:00:00-04:00
---

# 检查数字是否有小数位
> Checks if a number has any decimals digits

- 使用模 (`%`) 运算符检查数字是否可被 `1` 整除并返回结果。

```js
const hasDecimals = num => num % 1 !== 0;
```

```js
hasDecimals(1); // false
hasDecimals(1.001); // true
```
