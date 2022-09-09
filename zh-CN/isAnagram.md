---
title: 检测字符串是变位词(String is anagram)
tags: string,regexp
expertise: intermediate
cover: blog_images/new-york.jpg
firstSeen: 2018-02-19T15:47:47+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 检查一个字符串是否是另一个字符串的变位词（不区分大小写，忽略空格、标点符号和特殊字符）。
> Checks if a string is an anagram of another string (case-insensitive, ignores spaces, punctuation and special characters).

- 使用带有适当正则表达式的 `String.prototype.toLowerCase()` 和 `String.prototype.replace()` 来删除不必要的字符。
- 在两个字符串上使用 `String.prototype.split()`、`Array.prototype.sort()` 和 `Array.prototype.join()` 来规范化它们，然后检查它们的规范化形式是否相等。
- [变位词（百度百科）](https://baike.baidu.com/item/%E5%8F%98%E4%BD%8D%E8%AF%8D/3844597)

```js
const isAnagram = (str1, str2) => {
  const normalize = str =>
    str
      .toLowerCase()
      .replace(/[^a-z0-9]/gi, '')
      .split('')
      .sort()
      .join('');
  return normalize(str1) === normalize(str2);
};
```

```js
isAnagram('iceman', 'cinema'); // true
```
