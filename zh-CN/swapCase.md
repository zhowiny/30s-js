---
title: 交换大小写字符串(Swapcase string)
tags: string
expertise: beginner
author: maciv
cover: blog_images/mountain-lake-2.jpg
firstSeen: 2020-11-15T13:09:03+02:00
lastUpdated: 2020-11-15T13:09:03+02:00
---

### 创建一个将大写字符转换为小写字符的字符串，反之亦然。
> Creates a string with uppercase characters converted to lowercase and vice versa.

- 使用扩展运算符 (`...`) 将 `str` 转换为字符数组。
- 使用 `String.prototype.toLowerCase()` 和 `String.prototype.toUpperCase()` 将小写字符转换为大写，反之亦然。
- 使用 `Array.prototype.map()` 将转换应用于每个字符，`Array.prototype.join()` 组合回字符串。
- 请注意，`swapCase(swapCase(str)) === str` 不一定是为 `true`。

```js
const swapCase = str =>
  [...str]
    .map(c => (c === c.toLowerCase() ? c.toUpperCase() : c.toLowerCase()))
    .join('');
```

```js
swapCase('Hello world!'); // 'hELLO WORLD!'
```
