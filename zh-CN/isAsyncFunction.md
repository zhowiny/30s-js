---
title: 值是异步函数(Value is async function)
tags: type,function
expertise: intermediate
author: chalarangelo
cover: blog_images/interior-12.jpg
firstSeen: 2020-08-07T15:41:55+03:00
lastUpdated: 2020-10-20T11:21:07+03:00
---

# 检查给定的参数是否是一个 `async` 函数。
> Checks if the given argument is an `async` function.

- 使用 `Object.prototype.toString()` 和 `Function.prototype.call()` 并检查结果是否为 `'[object AsyncFunction]'`。

```js
const isAsyncFunction = val =>
  Object.prototype.toString.call(val) === '[object AsyncFunction]';
```

```js
isAsyncFunction(function() {}); // false
isAsyncFunction(async function() {}); // true
```
