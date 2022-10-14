---
title: 截断字符串(Truncate string)
tags: string
expertise: beginner
cover: blog_images/bamboo-lamp.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-21T21:17:45+03:00
---

# 将字符串截断到指定长度。
> Truncates a string up to a specified length.

- 确定 `String.prototype.length` 是否大于 `num`。
- 返回截断到所需长度的字符串，并在末尾或原始字符串后面附加 `...`。

```js
const truncateString = (str, num) =>
  str.length > num ? str.slice(0, num > 3 ? num - 3 : num) + '...' : str;
```

```js
truncateString('boomerang', 7); // 'boom...'
```
