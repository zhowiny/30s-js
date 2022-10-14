---
title: 值是数字(Value is number)
tags: type,math
expertise: beginner
cover: blog_images/red-petals.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 检查给定参数是否为数字。
> Checks if the given argument is a number.

- 使用 `typeof` 检查一个值是否被归类为数字原始类型。
- 为了防止 `NaN`，检查 `val === val`（因为 `NaN` 的 `typeof` 等于 `number` 并且是唯一不等于自身的值）。

```js
const isNumber = val => typeof val === 'number' && val === val;
```

```js
isNumber(1); // true
isNumber('1'); // false
isNumber(NaN); // false
```
