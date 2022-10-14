---
title: 解码 Base64 编码的字符串(Decode Base64 encoded string)
tags: node,string
expertise: beginner
cover: blog_images/thread.jpg
firstSeen: 2018-01-17T21:43:21+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 解码使用 base-64 编码的数据字符串。
> Decodes a string of data which has been encoded using base-64 encoding.

- 使用 base-64 编码为给定的字符串创建一个 `Buffer`。
- 使用 `Buffer.prototype.toString()` 返回解码后的字符串。

```js
const atob = str => Buffer.from(str, 'base64').toString('binary');
```

```js
atob('Zm9vYmFy'); // 'foobar'
```
