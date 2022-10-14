---
title: 字符串是小写的(String is lowercase)
tags: string
expertise: beginner
cover: blog_images/flower-portrait-7.jpg
firstSeen: 2018-01-06T11:16:05+02:00
lastUpdated: 2020-10-20T11:21:07+03:00
---

# 检查字符串是否为小写。
> Checks if a string is lower case.

- 使用 `String.prototype.toLowerCase()` 将给定的字符串转换为小写，并将其与原始字符串进行比较。

```js
const isLowerCase = str => str === str.toLowerCase();
```

```js
isLowerCase('abc'); // true
isLowerCase('a3@$'); // true
isLowerCase('Ab4'); // false
```
