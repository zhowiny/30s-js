---
title: 序列化 cookie(Serialize cookie)
tags: browser,string
expertise: intermediate
cover: blog_images/three-vases.jpg
firstSeen: 2018-01-13T14:19:21+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 将 cookie 名称-值对序列化为 Set-Cookie 标头字符串。
> Serializes a cookie name-value pair into a Set-Cookie header string.

- 使用模板文字和 `encodeURIComponent()` 创建适当的字符串。

```js
const serializeCookie = (name, val) =>
  `${encodeURIComponent(name)}=${encodeURIComponent(val)}`;
```

```js
serializeCookie('foo', 'bar'); // 'foo=bar'
```
