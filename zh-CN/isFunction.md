---
title: 值是函数(Value is function)
tags: type,function
expertise: beginner
cover: blog_images/boulder-beach.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

### 检查给定的参数是否是一个函数。
> Checks if the given argument is a function.

- 使用 `typeof` 来检查一个值类型是否为函数原始类型。

```js
const isFunction = val => typeof val === 'function';
```

```js
isFunction('x'); // false
isFunction(x => x); // true
```
