---
title: 生成 UUID（浏览器）(Generate UUID (browser))
tags: browser,random
expertise: intermediate
cover: blog_images/mountain-lake-cottage.jpg
firstSeen: 2017-12-29T09:47:10+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

# 在浏览器中生成 UUID。
> Generates a UUID in a browser.

- 使用 `Crypto.getRandomValues()` 生成符合 [RFC4122](https://www.ietf.org/rfc/rfc4122.txt) 版本 4 的 UUID。
- 使用 `Number.prototype.toString()` 将其转换为正确的 UUID（十六进制字符串）。

```js
const UUIDGeneratorBrowser = () =>
  ([1e7] + -1e3 + -4e3 + -8e3 + -1e11).replace(/[018]/g, c =>
    (
      c ^
      (crypto.getRandomValues(new Uint8Array(1))[0] & (15 >> (c / 4)))
    ).toString(16)
  );
```

```js
UUIDGeneratorBrowser(); // '7982fcfe-5721-4632-bede-6000885be57d'
```
