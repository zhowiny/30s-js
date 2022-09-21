---
title: 验证数字(Validate number)
tags: math
expertise: intermediate
cover: blog_images/flower-portrait-9.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:23:26+03:00
---

### 检查给定值是否为数字。
> Checks if the given value is a number.

- 使用 `parseFloat()` 尝试将 `n` 转换为数字。
- 使用 `Number.isNaN()` 和逻辑非 (`!`) 运算符来检查 `num` 是否为数字。
- 使用 `Number.isFinite()` 来检查 `num` 是否是有限的。
- 使用 `Number` 和松散相等运算符 (`==`) 检查强制是否成立。

```js
const validateNumber = n => {
  const num = parseFloat(n);
  return !Number.isNaN(num) && Number.isFinite(num) && Number(n) == n;
}
```

```js
validateNumber('10'); // true
validateNumber('a'); // false
```
