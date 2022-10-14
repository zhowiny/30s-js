---
title: 解析 cookie(Parse cookie)
tags: browser,string
expertise: intermediate
cover: blog_images/three-vases.jpg
firstSeen: 2018-01-13T14:19:21+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 解析 HTTP Cookie 标头字符串，返回所有 cookie 名称-值对的对象。
> Parses an HTTP Cookie header string, returning an object of all cookie name-value pairs.

- 使用 `String.prototype.split()` 将键值对彼此分开。
- 使用 `Array.prototype.map()` 和 `String.prototype.split()` 将每对中的键与值分开。
- 使用 `Array.prototype.reduce()` 和 `decodeURIComponent()` 创建一个包含所有键值对的对象。

```js
const parseCookie = str =>
  str
    .split(';')
    .map(v => v.split('='))
    .reduce((acc, v) => {
      acc[decodeURIComponent(v[0].trim())] = decodeURIComponent(v[1].trim());
      return acc;
    }, {});
```

```js
parseCookie('foo=bar; equation=E%3Dmc%5E2');
// { foo: 'bar', equation: 'E=mc^2' }
```
