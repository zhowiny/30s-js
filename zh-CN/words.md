---
title: 字符串转单词(String to words)
tags: string,regexp
expertise: intermediate
cover: blog_images/sea-view-2.jpg
firstSeen: 2017-12-21T14:50:57+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

# 将给定的字符串转换为单词数组。
> Converts a given string into an array of words.

- 将 `String.prototype.split()` 与提供的 `pattern` 一起使用（默认为非 alpha 作为正则表达式）以转换为字符串数组。
- 使用 `Array.prototype.filter()` 删除任何空字符串。
- 省略第二个参数，`pattern`，使用默认的正则表达式。

```js
const words = (str, pattern = /[^a-zA-Z-]+/) =>
  str.split(pattern).filter(Boolean);
```

```js
words('I love javaScript!!'); // ['I', 'love', 'javaScript']
words('python, javaScript & coffee'); // ['python', 'javaScript', 'coffee']
```
