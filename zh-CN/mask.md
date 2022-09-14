---
title: 屏蔽一个值(Mask a value)
tags: string
expertise: intermediate
cover: blog_images/rocky-beach-3.jpg
firstSeen: 2018-01-01T13:02:59+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 用指定的掩码字符替换除最后一个字符之外的所有字符。
> Replaces all but the last `num` of characters with the specified mask character.

- 使用 `String.prototype.slice()` 来抓取将保持未屏蔽的字符部分。
- 使用 `String.prototype.padStart()` 用 `mask` 字符填充字符串的开头直到原始长度。
- 如果 `num` 为负数，则未屏蔽的字符将位于字符串的开头。
- 省略第二个参数 `num` ，以保持默认的 `4` 个字符不被屏蔽。
- 省略第三个参数 `mask`，使用默认字符 `'*'` 作为掩码。

```js
const mask = (cc, num = 4, mask = '*') =>
  `${cc}`.slice(-num).padStart(`${cc}`.length, mask);
```

```js
mask(1234567890); // '******7890'
mask(1234567890, 3); // '*******890'
mask(1234567890, -4, '$'); // '$$$$567890'
```
