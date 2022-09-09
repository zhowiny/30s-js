---
title: 浏览器中计算 SHA-256 哈希(Calculate SHA-256 hash (browser))
tags: browser,promise
expertise: advanced
cover: blog_images/padlocks.jpg
firstSeen: 2018-01-17T14:09:01+02:00
lastUpdated: 2021-10-13T19:29:39+02:00
---

### 使用 [SHA-256](https://en.wikipedia.org/wiki/SHA-2) 算法为值创建哈希。返回一个 `Promise`。
> Creates a hash for a value using the [SHA-256](https://en.wikipedia.org/wiki/SHA-2) algorithm.
> Returns a promise.

- 使用 [SubtleCrypto](https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto) API 为给定值创建哈希。
- 创建一个新的 `TextEncoder` 并使用它来编码 `val`。 将其值传递给“SubtleCrypto.digest()”以生成给定数据的摘要。
- 使用 `DataView.prototype.getUint32()` 从解析的 `ArrayBuffer` 中读取数据。
- 使用 `Number.prototype.toString()` 将数据转换为其十六进制表示。 使用 `Array.prototype.push()` 将数据添加到数组中。
- 最后，使用 `Array.prototype.join()` 将 `hexes` 数组中的值组合成一个字符串。

```js
const hashBrowser = val =>
  crypto.subtle
    .digest('SHA-256', new TextEncoder('utf-8').encode(val))
    .then(h => {
      let hexes = [],
        view = new DataView(h);
      for (let i = 0; i < view.byteLength; i += 4)
        hexes.push(('00000000' + view.getUint32(i).toString(16)).slice(-8));
      return hexes.join('');
    });
```

```js
hashBrowser(
  JSON.stringify({ a: 'a', b: [1, 2, 3, 4], foo: { c: 'bar' } })
).then(console.log);
// '04aa106279f5977f59f9067fa9712afc4aedc6f5862a8defc34552d8c7206393'
```
