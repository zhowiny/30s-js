---
title: 扩展十六进制值(Extend hex value)
tags: string
expertise: intermediate
cover: blog_images/red-mountain.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

### 将 3 位颜色代码扩展为 6 位颜色代码。
> Extends a 3-digit color code to a 6-digit color code.

- 使用 `Array.prototype.map()`、`String.prototype.split()` 和 `Array.prototype.join()` 来加入映射数组，以将 3 位 RGB 表示的十六进制颜色代码转换为 6位表格。
- `Array.prototype.slice()` 用于从字符串开头删除 `#`，因为它已添加一次。

```js
const extendHex = shortHex =>
  '#' +
  shortHex
    .slice(shortHex.startsWith('#') ? 1 : 0)
    .split('')
    .map(x => x + x)
    .join('');
```

```js
extendHex('#03f'); // '#0033ff'
extendHex('05a'); // '#0055aa'
```
