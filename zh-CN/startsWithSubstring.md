---
title: 字符串以子字符串开头(String starts with substring)
shortTitle: Starts with substring
tags: string
expertise: beginner
cover: blog_images/boutique-home-office-3.jpg
author: chalarangelo
firstSeen: 2022-07-31T05:00:00-04:00
---

### 检查给定字符串是否以另一个字符串的子字符串开头。
> Checks if a given string starts with a substring of another string.

- 使用 `for...in` 循环和 `String.prototype.slice()` 来获取给定 `word` 的每个子字符串，从开头开始。
- 使用 `String.prototype.startsWith()` 对照 `text` 检查当前子字符串。
- 如果找到，则返回匹配的子字符串。 否则，返回 `undefined`。

```js
const startsWithSubstring = (text, word) => {
  for (let i in word) {
    const substr = word.slice(-i - 1);
    if (text.startsWith(substr)) return substr;
  }
  return undefined;
};
```

```js
startsWithSubstring('/>Lorem ipsum dolor sit amet', '<br />'); // '/>'
```
