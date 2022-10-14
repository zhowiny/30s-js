---
title: 压缩和拼接数组(Compact and join array)
tags: array
expertise: intermediate
author: chalarangelo
cover: blog_images/racoon.jpg
firstSeen: 2022-04-08T05:00:00-04:00
---

# 从数组中删除虚假值，并将其余值结合到字符串中。
> Removes falsy values from an array and combines the remaining values into a string.

- 使用 `Array.prototype.filter()` 过滤掉虚假值（`false`、`null`、`0`、`""`、`undefined` 和 `NaN`）。
- 使用 `Array.prototype.join()` 将剩余的值连接成一个字符串。

```js
const compactJoin = (arr, delim = ',') => arr.filter(Boolean).join(delim);
```

```js
compactJoin(['a', '', 'b', 'c']); // 'a,b,c'
```
