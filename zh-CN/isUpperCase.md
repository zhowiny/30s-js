---
title: 字符串为大写(String is uppercase)
tags: string
expertise: beginner
cover: blog_images/flower-portrait-7.jpg
firstSeen: 2018-01-06T11:16:05+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 检查字符串是否为大写。
> Checks if a string is upper case.

- 使用 `String.prototype.toUpperCase()` 将给定的字符串转换为大写，并将其与原始字符串进行比较。

```js
const isUpperCase = str => str === str.toUpperCase();
```

```js
isUpperCase('ABC'); // true
isUpperCase('A3@$'); // true
isUpperCase('aB4'); // false
```
