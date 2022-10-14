---
title: 数字为负零(Number is negative zero)
tags: math
expertise: intermediate
cover: blog_images/flower-portrait-8.jpg
firstSeen: 2018-11-12T15:45:36+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 检查给定值是否等于负零（`-0`）。
> Checks if the given value is equal to negative zero (`-0`).

- 检查传递的值是否等于 `0` ，以及 `1` 除以该值是否等于 `-Infinity`。

```js
const isNegativeZero = val => val === 0 && 1 / val === -Infinity;
```

```js
isNegativeZero(-0); // true
isNegativeZero(0); // false
```
