---
title: 转义正则表达式(Escape RegExp)
tags: string,regexp
expertise: intermediate
cover: blog_images/frog-blue-flower.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

### 转义要在正则表达式中使用的字符串。
> Escapes a string to use in a regular expression.

- 使用 `String.prototype.replace()` 转义特殊字符。

```js
const escapeRegExp = str => str.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');
```

```js
escapeRegExp('(test)'); // \\(test\\)
```
