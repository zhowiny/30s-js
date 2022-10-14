---
title: 规范化行尾(Normalize line endings)
tags: string,regexp
expertise: intermediate
author: chalarangelo
cover: blog_images/red-light.jpg
firstSeen: 2020-05-04T12:33:13+03:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

# 规范化字符串中的行尾。
> Normalizes line endings in a string.

- 使用 `String.prototype.replace()` 和正则表达式来匹配和替换行尾为 `normalized` 版本。
- 省略第二个参数 `normalized`，以使用默认值 `'\r\n'`。

```js
const normalizeLineEndings = (str, normalized = '\r\n') =>
  str.replace(/\r?\n/g, normalized);
```

```js
normalizeLineEndings('This\r\nis a\nmultiline\nstring.\r\n');
// 'This\r\nis a\r\nmultiline\r\nstring.\r\n'
normalizeLineEndings('This\r\nis a\nmultiline\nstring.\r\n', '\n');
// 'This\nis a\nmultiline\nstring.\n'
```
