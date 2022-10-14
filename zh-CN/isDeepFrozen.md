---
title: 检查对象是否被深度冻结(Check if object is deep frozen)
tags: object,recursion
expertise: intermediate
author: maciv
cover: blog_images/godray-computer-mug.jpg
firstSeen: 2020-09-04T20:20:11+03:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 检查对象是否被深度冻结。
> Checks if an object is deeply frozen.

- 使用递归。
- 在给定对象上使用 `Object.isFrozen()`。
- 使用 `Object.keys()`、`Array.prototype.every()` 检查所有键是深度冻结的对象还是非对象值。

```js
const isDeepFrozen = obj =>
  Object.isFrozen(obj) &&
  Object.keys(obj).every(
    prop => typeof obj[prop] !== 'object' || isDeepFrozen(obj[prop])
  );
```

```js
const x = Object.freeze({ a: 1 });
const y = Object.freeze({ b: { c: 2 } });
isDeepFrozen(x); // true
isDeepFrozen(y); // false
```
