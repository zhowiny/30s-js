---
title: 数字化(Digitize number)
tags: math
expertise: beginner
cover: blog_images/industrial-tokyo.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-18T14:58:09+03:00
---

### 将数字转换为数字数组，必要时删除其符号。
> Converts a number to an array of digits, removing its sign if necessary.

- 使用 `Math.abs()` 去除数字的符号。
- 将数字转换为字符串，使用扩展运算符 (`...`) 构建数组。
- 使用 `Array.prototype.map()` 和 `parseInt()` 将每个值转换为整数。

```js
const digitize = n => [...`${Math.abs(n)}`].map(i => parseInt(i));
```

```js
digitize(123); // [1, 2, 3]
digitize(-123); // [1, 2, 3]
```
