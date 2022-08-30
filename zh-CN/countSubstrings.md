---
title: 计算字符串的子串(Count substrings of string)
tags: string,algorithm
expertise: beginner
author: chalarangelo
cover: blog_images/obelisk.jpg
firstSeen: 2020-12-31T13:58:51+02:00
lastUpdated: 2021-01-08T00:23:44+02:00
---

### 计算给定字符串中子字符串的出现次数。
> Counts the occurrences of a substring in a given string.

- 使用 `Array.prototype.indexOf()` 在 `str` 中查找 `searchValue`。
- 如果找到该值，则增加一个计数器并更新索引，`i`。
- 使用 `while` 循环，只要从 `Array.prototype.indexOf()` 返回的值为 `-1`，该循环就会返回。

```js
const countSubstrings = (str, searchValue) => {
  let count = 0,
    i = 0;
  while (true) {
    const r = str.indexOf(searchValue, i);
    if (r !== -1) [count, i] = [count + 1, r + 1];
    else return count;
  }
};
```

```js
countSubstrings('tiktok tok tok tik tok tik', 'tik'); // 3
countSubstrings('tutut tut tut', 'tut'); // 4
```
