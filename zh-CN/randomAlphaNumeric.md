---
title: 随机字母数字字符串(Random alphanumeric string)
tags: string,random
expertise: advanced
cover: blog_images/interior-5.jpg
firstSeen: 2020-10-06T18:33:29+03:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 生成具有指定长度的随机字符串。
> Generates a random string with the specified length.

- 使用 `Array.from()` 创建一个具有指定 `length` 的新数组。
- 使用 `Math.random()` 生成一个随机浮点数。
- 使用带有 `radix` 值为 `36` 的 `Number.prototype.toString()` 将其转换为字母数字字符串。
- 使用 `String.prototype.slice()` 从每个生成的数字中删除整数部分和小数点。
- 使用 `Array.prototype.some()` 根据需要多次重复此过程，直到 `length`，因为它每次都会产生一个可变长度的字符串。
- 最后，使用 `String.prototype.slice()` 修剪生成的字符串，如果它比给定的 `length` 长。

```js
const randomAlphaNumeric = length => {
  let s = '';
  Array.from({ length }).some(() => {
    s += Math.random().toString(36).slice(2);
    return s.length >= length;
  });
  return s.slice(0, length);
};
```

```js
randomAlphaNumeric(5); // '0afad'
```
