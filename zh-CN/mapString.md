---
title: 映射字符串(Map string)
tags: string
expertise: intermediate
cover: blog_images/budapest-palace.jpg
firstSeen: 2018-07-14T10:59:56+03:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 使用对给定字符串中的每个字符调用提供的函数的结果创建一个新字符串。
> Creates a new string with the results of calling a provided function on every character in the given string.

- 使用 `String.prototype.split()` 和 `Array.prototype.map()` 为 `str` 中的每个字符调用提供的函数 `fn`。
- 使用 `Array.prototype.join()` 将字符数组重新组合成一个字符串。
- 回调函数`fn`接受三个参数（当前字符、当前字符的索引和字符串`mapString`被调用）。

```js
const mapString = (str, fn) =>
  str
    .split('')
    .map((c, i) => fn(c, i, str))
    .join('');
```

```js
mapString('lorem ipsum', c => c.toUpperCase()); // 'LOREM IPSUM'
```
