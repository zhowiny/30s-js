---
title: 克隆正则表达式(Clone RegExp)
tags: type
expertise: intermediate
cover: blog_images/tomatoes.jpg
firstSeen: 2018-01-01T19:45:47+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 克隆一个正则表达式。
> Clones a regular expression.

- 使用 `RegExp` 构造函数、`RegExp.prototype.source` 和 `RegExp.prototype.flags` 来克隆给定的正则表达式。

```js
const cloneRegExp = regExp => new RegExp(regExp.source, regExp.flags);
```

```js
const regExp = /lorem ipsum/gi;
const regExp2 = cloneRegExp(regExp); // regExp !== regExp2
```
