---
title: 不区分大小写的子字符串搜索(Case-insensitive substring search)
tags: string
expertise: beginner
author: chalarangelo
cover: blog_images/cup-of-orange.jpg
firstSeen: 2022-07-28T05:00:00-04:00
---

# 检查字符串是否包含子字符串，不区分大小写。
> Checks if a string contains a substring, case-insensitive.

- 使用带有 `'i'` 标志的 `RegExp` 构造函数来创建一个匹配给定 `searchString` 的正则表达式，忽略大小写。
- 使用 `RegExp.prototype.test()` 检查字符串是否包含子字符串。

```js
const includesCaseInsensitive = (str, searchString) =>
  new RegExp(searchString, 'i').test(str);
```

```js
includesCaseInsensitive('Blue Whale', 'blue'); // true
```
