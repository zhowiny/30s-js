---
title: 子串索引(Index of substrings)
tags: string,algorithm,generator
expertise: intermediate
author: chalarangelo
cover: blog_images/violin.jpg
firstSeen: 2020-12-31T13:58:51+02:00
lastUpdated: 2020-12-31T13:58:51+02:00
---

### 查找给定字符串中子字符串的所有索引。
> Finds all the indexes of a substring in a given string.

- 使用 `Array.prototype.indexOf()` 在 `str` 中查找 `searchValue`。
- 如果找到值，则使用`yield`返回索引并更新索引`i`。
- 使用 `while` 循环，一旦 `Array.prototype.indexOf()` 返回的值为 `-1`，该循环将终止生成器。

```js
const indexOfSubstrings = function* (str, searchValue) {
  let i = 0;
  while (true) {
    const r = str.indexOf(searchValue, i);
    if (r !== -1) {
      yield r;
      i = r + 1;
    } else return;
  }
};
```

```js
[...indexOfSubstrings('tiktok tok tok tik tok tik', 'tik')]; // [0, 15, 23]
[...indexOfSubstrings('tutut tut tut', 'tut')]; // [0, 2, 6, 10]
[...indexOfSubstrings('hello', 'hi')]; // []
```
