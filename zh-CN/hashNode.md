---
title: Nodejs中计算 SHA-256 哈希(Calculate SHA-256 hash (Node.js))
tags: node,promise
expertise: advanced
cover: blog_images/padlocks.jpg
firstSeen: 2018-01-17T14:09:01+02:00
lastUpdated: 2021-10-13T19:29:39+02:00
---

# 使用 [SHA-256](https://en.wikipedia.org/wiki/SHA-2) 算法为值创建哈希。返回一个承诺。
> Creates a hash for a value using the [SHA-256](https://en.wikipedia.org/wiki/SHA-2) algorithm.
> Returns a promise.

- 使用 `crypto.createHash()` 使用适当的算法创建一个 `Hash` 对象。
- 使用 `hash.update()` 将 `val` 中的数据添加到 `Hash`，`hash.digest()` 计算数据的摘要。
- 使用 `setTimeout()` 来防止长时间操作的阻塞。 返回一个 `Promise` 给它一个熟悉的界面。

```js
const crypto = require('crypto');

const hashNode = val =>
  new Promise(resolve =>
    setTimeout(
      () => resolve(crypto.createHash('sha256').update(val).digest('hex')),
      0
    )
  );
```

```js
hashNode(JSON.stringify({ a: 'a', b: [1, 2, 3, 4], foo: { c: 'bar' } })).then(
  console.log
);
// '04aa106279f5977f59f9067fa9712afc4aedc6f5862a8defc34552d8c7206393'
```
