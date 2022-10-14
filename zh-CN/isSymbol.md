---
title: 值是symbol(Value is symbol)
tags: type
expertise: beginner
cover: blog_images/naming-conventions.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 检查给定的参数是否是 `symbol`。
> Checks if the given argument is a symbol.

- 使用 `typeof` 来检查一个值是否被归类为 `symbol`原始类型。

```js
const isSymbol = val => typeof val === 'symbol';
```

```js
isSymbol(Symbol('x')); // true
```
