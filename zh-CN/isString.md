---
title: 值是字符串(Value is string)
tags: type,string
expertise: beginner
cover: blog_images/overgrown.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 检查给定参数是否为字符串。仅适用于字符串原始类型。
> Checks if the given argument is a string.
> Only works for string primitives.

- 使用 `typeof` 来检查一个值是否被归类为字符串原始类型。

```js
const isString = val => typeof val === 'string';
```

```js
isString('10'); // true
```
