---
title: 字符串以子字符串结尾(String ends with substring)
shortTitle: Ends with substring
tags: string
expertise: beginner
cover: blog_images/boutique-home-office-4.jpg
author: chalarangelo
firstSeen: 2022-08-01T05:00:00-04:00
---

### 检查给定字符串是否以另一个字符串的子字符串结尾。
> Checks if a given string ends with a substring of another string.

- 使用 `for...in` 循环和 `String.prototype.slice()` 来获取给定 `word` 的每个子字符串，从末尾开始。
- 使用 `String.prototype.endsWith()` 对照 `text` 检查当前子字符串。
- 如果找到，则返回匹配的子字符串。 否则，返回 `undefined`。

```js
const endsWithSubstring = (text, word) => {
  for (let i in word) {
    const substr = word.slice(0, i + 1);
    if (text.endsWith(substr)) return substr;
  }
  return undefined;
};
```

```js
endsWithSubstring('Lorem ipsum dolor sit amet<br /', '<br />'); // '<br /'
```
