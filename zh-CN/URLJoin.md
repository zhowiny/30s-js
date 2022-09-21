---
title: 连接 URL 段(Join URL segments)
tags: string,regexp
expertise: advanced
cover: blog_images/digital-nomad-2.jpg
firstSeen: 2018-01-16T15:53:03+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

### 将所有给定的 URL 段连接在一起，然后规范化生成的 URL。
> Joins all given URL segments together, then normalizes the resulting URL.

- 使用 `Array.prototype.join()` 来组合 URL 段。
- 使用一系列带有各种正则表达式的 `String.prototype.replace()` 调用来规范化生成的 URL（删除双斜杠，为协议添加适当的斜杠，删除参数前的斜杠，将参数与 `'&'` 组合并规范化第一个参数分隔符）。

```js
const URLJoin = (...args) =>
  args
    .join('/')
    .replace(/[\/]+/g, '/')
    .replace(/^(.+):\//, '$1://')
    .replace(/^file:/, 'file:/')
    .replace(/\/(\?|&|#[^!])/g, '$1')
    .replace(/\?/g, '&')
    .replace('&', '?');
```

```js
URLJoin('http://www.google.com', 'a', '/b/cd', '?foo=123', '?bar=foo');
// 'http://www.google.com/a/b/cd?foo=123&bar=foo'
```
