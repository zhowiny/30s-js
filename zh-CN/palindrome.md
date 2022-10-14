---
title: 回文字符串(Palindrome)
tags: string
expertise: intermediate
cover: blog_images/bridge-drop.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 检查给定的字符串是否是回文。
> Checks if the given string is a palindrome.

- 将字符串规范化为 `String.prototype.toLowerCase()` 并使用 `String.prototype.replace()` 从中删除非字母数字字符。
- 使用扩展运算符 (`...`) 将规范化字符串拆分为单个字符。
- 使用 `Array.prototype.reverse()`、`Array.prototype.join()` 并将结果与标准化字符串进行比较。

```js
const palindrome = str => {
  const s = str.toLowerCase().replace(/[\W_]/g, '');
  return s === [...s].reverse().join('');
};
```

```js
palindrome('taco cat'); // true
```
