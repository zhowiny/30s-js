---
title: 删除非 ASCII 字符(Remove non ASCII characters)
tags: string,regexp
expertise: intermediate
cover: blog_images/tram-car.jpg
firstSeen: 2018-01-26T14:00:54+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 删除不可打印的 ASCII 字符。
> Removes non-printable ASCII characters.

- 使用带有正则表达式的 `String.prototype.replace()` 来删除不可打印的 ASCII 字符。

```js
const removeNonASCII = str => str.replace(/[^\x20-\x7E]/g, '');
```

```js
removeNonASCII('äÄçÇéÉêlorem-ipsumöÖÐþúÚ'); // 'lorem-ipsum'
```
