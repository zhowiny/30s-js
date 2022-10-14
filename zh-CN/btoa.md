---
title: 将字符串编码为 Base64(Encode string to Base64)
tags: node,string
expertise: beginner
cover: blog_images/laptop-journey.jpg
firstSeen: 2018-01-17T21:43:21+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 从 String 对象创建 base-64 编码的 ASCII 字符串，其中字符串中的每个字符都被视为二进制数据的一个字节。
> Creates a base-64 encoded ASCII string from a String object in which each character in the string is treated as a byte of binary data.

- 使用二进制编码为给定的字符串创建一个 `Buffer` 。
- 使用 `Buffer.prototype.toString()` 返回 base-64 编码的字符串。

```js
const btoa = str => Buffer.from(str, 'binary').toString('base64');
```

```js
btoa('foobar'); // 'Zm9vYmFy'
```
