---
title: 值是生成器函数(Value is generator function)
tags: type,function
expertise: intermediate
author: chalarangelo
cover: blog_images/interior-4.jpg
firstSeen: 2020-08-07T15:40:38+03:00
lastUpdated: 2020-10-20T11:21:07+03:00
---

### 检查给定参数是否是生成器函数。
> Checks if the given argument is a generator function.

- 使用 `Object.prototype.toString()` 和 `Function.prototype.call()` 并检查结果是否为 `'[object GeneratorFunction]'`。

```js
const isGeneratorFunction = val =>
  Object.prototype.toString.call(val) === '[object GeneratorFunction]';
```

```js
isGeneratorFunction(function() {}); // false
isGeneratorFunction(function*() {}); // true
```
