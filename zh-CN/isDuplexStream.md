---
title: 是否是双工流(Stream is duplex)
tags: node,type
expertise: intermediate
cover: blog_images/digital-nomad-11.jpg
firstSeen: 2018-10-03T22:16:10+03:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 检查给定参数是否是双工（可读和可写）流。
> Checks if the given argument is a duplex (readable and writable) stream.

- 检查值是否不同于 `null`。
- 使用 `typeof` 检查值是否属于 `object` 类型，并且 `pipe` 属性是否属于 `function` 类型。
- 另外检查 `_read`、`_write` 和 `_readableState`、`_writableState` 属性的 `typeof` 是否分别是 `function` 和 `object`。

```js
const isDuplexStream = val =>
  val !== null &&
  typeof val === 'object' &&
  typeof val.pipe === 'function' &&
  typeof val._read === 'function' &&
  typeof val._readableState === 'object' &&
  typeof val._write === 'function' &&
  typeof val._writableState === 'object';
```

```js
const Stream = require('stream');

isDuplexStream(new Stream.Duplex()); // true
```
