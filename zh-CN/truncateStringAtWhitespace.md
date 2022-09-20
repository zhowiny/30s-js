---
title: 在空格处截断字符串(Truncate string at whitespace)
tags: string
expertise: intermediate
cover: blog_images/cloudy-mountaintop-2.jpg
firstSeen: 2020-10-19T11:11:16+03:00
lastUpdated: 2020-10-21T21:17:45+03:00
---

### 将字符串截断到指定长度，尽可能考虑空格。
> Truncates a string up to specified length, respecting whitespace when possible.

- 确定 `String.prototype.length` 是否大于或等于 `lim`。 如果没有，请按原样返回。
- 使用 `String.prototype.slice()` 和 `String.prototype.lastIndexOf()` 查找所需 `lim` 下方最后一个空格的索引。
- 使用 `String.prototype.slice()` 根据 `lastSpace` 适当地截断 `str`，如果可能的话尊重空格并在末尾附加 `ending`。
- 省略第三个参数 `ending`，以使用默认的 `'...'` 结尾。

```js
const truncateStringAtWhitespace = (str, lim, ending = '...') => {
  if (str.length <= lim) return str;
  const lastSpace = str.slice(0, lim - ending.length + 1).lastIndexOf(' ');
  return str.slice(0, lastSpace > 0 ? lastSpace : lim - ending.length) + ending;
};
```

```js
truncateStringAtWhitespace('short', 10); // 'short'
truncateStringAtWhitespace('not so short', 10); // 'not so...'
truncateStringAtWhitespace('trying a thing', 10); // 'trying...'
truncateStringAtWhitespace('javascripting', 10); // 'javascr...'
```
