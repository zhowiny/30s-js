---
title: 流是可写的(Stream is writable)
tags: node,type
expertise: intermediate
cover: blog_images/digital-nomad-3.jpg
firstSeen: 2018-10-03T22:16:10+03:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 检查给定参数是否是可写流。
> Checks if the given argument is a writable stream.

- 检查值是否不同于 `null`。
- 使用`typeof`检查值是否为`object`类型，`pipe`属性是否为`function`类型。
- 另外检查 `typeof` 和 `_write` 和 `_writableState` 属性是否分别是 `function` 和 `object`。

```js
const isWritableStream = val =>
  val !== null &&
  typeof val === 'object' &&
  typeof val.pipe === 'function' &&
  typeof val._write === 'function' &&
  typeof val._writableState === 'object';
```

```js
const fs = require('fs');

isWritableStream(fs.createWriteStream('test.txt')); // true
```
