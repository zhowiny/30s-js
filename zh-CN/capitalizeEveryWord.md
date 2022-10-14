---
title: 将每个单词大写(Capitalize every word)
tags: string,regexp
expertise: intermediate
cover: blog_images/laptop-plants.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 将字符串中每个单词的首字母大写。
> Capitalizes the first letter of every word in a string.

- 使用 `String.prototype.replace()` 匹配每个单词的第一个字符，并使用 `String.prototype.toUpperCase()` 将其大写。

```js
const capitalizeEveryWord = str =>
  str.replace(/\b[a-z]/g, char => char.toUpperCase());
```

```js
capitalizeEveryWord('hello world!'); // 'Hello World!'
```
