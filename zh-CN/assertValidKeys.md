---
title: 验证对象的`keys`是否有效(Assert object keys are valid)
tags: object
expertise: intermediate
author: chalarangelo
cover: blog_images/river-flow.jpg
firstSeen: 2021-07-18T05:00:00-04:00
---

# 验证对象中的所有键与给定的 `keys` 匹配。
> Validates all keys in an object match the given `keys`.

- 使用 `Object.keys()` 获取给定对象 `obj` 的键。
- 使用 `Array.prototype.every()` 和 `Array.prototype.includes()` 来验证对象中的每个键是否在 `keys` 数组中指定。

```js
const assertValidKeys = (obj, keys) =>
  Object.keys(obj).every(key => keys.includes(key));
```

```js
assertValidKeys({ id: 10, name: 'apple' }, ['id', 'name']); // true
assertValidKeys({ id: 10, name: 'apple' }, ['id', 'type']); // false
```
