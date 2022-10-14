---
title: 生成 UUID (Node.js)(Generate UUID (Node.js))
tags: node,random
expertise: intermediate
cover: blog_images/digital-nomad-7.jpg
firstSeen: 2017-12-29T09:47:10+02:00
lastUpdated: 2022-03-14T17:41:43+03:00
---

# 在 Node.JS 中生成 UUID。
> Generates a UUID in Node.JS.

- 使用 `crypto.randomBytes()` 生成符合 [RFC4122](https://www.ietf.org/rfc/rfc4122.txt) 版本 4 的 UUID。
- 使用 `Number.prototype.toString()` 将其转换为正确的 UUID（十六进制字符串）。
- [`crypto.randomUUID()`](https://nodejs.org/api/crypto.html#cryptorandomuuidoptions) 提供了类似的功能。

```js
const crypto = require('crypto');

const UUIDGeneratorNode = () =>
  ([1e7] + -1e3 + -4e3 + -8e3 + -1e11).replace(/[018]/g, c =>
    (c ^ (crypto.randomBytes(1)[0] & (15 >> (c / 4)))).toString(16)
  );
```

```js
UUIDGeneratorNode(); // '79c7c136-60ee-40a2-beb2-856f1feabefc'
```
