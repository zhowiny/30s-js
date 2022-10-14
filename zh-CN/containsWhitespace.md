---
title: 检查字符串是否包含空格(Check if string contains whitespace)
tags: string,regexp
expertise: beginner
author: chalarangelo
cover: blog_images/bag-waiting.jpg
firstSeen: 2020-03-25T12:37:13+02:00
lastUpdated: 2020-10-18T23:04:45+03:00
---

# 检查给定的字符串是否包含任何空白字符。
> Checks if the given string contains any whitespace characters.

- 使用 `RegExp.prototype.test()` 和适当的正则表达式来检查给定的字符串是否包含任何空白字符。

```js
const containsWhitespace = str => /\s/.test(str);
```

```js
containsWhitespace('lorem'); // false
containsWhitespace('lorem ipsum'); // true
```
