---
title: 右子串生成器(Right substring generator)
tags: string,generator
expertise: intermediate
cover: blog_images/boutique-home-office-2.jpg
author: chalarangelo
firstSeen: 2022-07-25T05:00:00-04:00
---

# 生成给定字符串的所有正确子字符串。
> Generates all right substrings of a given string.

- 如果字符串为空，使用 `String.prototype.length` 提前终止。
- 使用 `for...in` 循环和 `String.prototype.slice()` 来 `yield` 给定字符串的每个子字符串，从末尾开始。

```js
const rightSubstrGenerator = function* (str) {
  if (!str.length) return;
  for (let i in str) yield str.slice(-i - 1);
};
```

```js
[...rightSubstrGenerator('hello')];
// [ 'o', 'lo', 'llo', 'ello', 'hello' ]
```
