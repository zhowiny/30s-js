---
title: 左子串生成器(Left substring generator)
tags: string,generator
expertise: intermediate
cover: blog_images/boutique-home-office-1.jpg
author: chalarangelo
firstSeen: 2022-07-24T05:00:00-04:00
---

### 生成给定字符串的所有左子字符串。
> Generates all left substrings of a given string.

- 如果字符串为空，使用 `String.prototype.length` 提前终止。
- 使用 `for...in` 循环和 `String.prototype.slice()` 来 `yield` 给定字符串的每个子字符串，从开头开始。

```js
const leftSubstrGenerator = function* (str) {
  if (!str.length) return;
  for (let i in str) yield str.slice(0, i + 1);
};
```

```js
[...leftSubstrGenerator('hello')];
// [ 'h', 'he', 'hel', 'hell', 'hello' ]
```
