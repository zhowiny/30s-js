---
title: 获取值的类型(Type of value)
tags: type
expertise: beginner
cover: blog_images/pink-flowers.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 返回值的原始类型。
> Returns the native type of a value.

- 如果值为 `undefined` 或 `null`，则返回 `'undefined'` 或 `'null'`。
- 否则，使用 `Object.prototype.constructor` 和 `Function.prototype.name` 获取构造函数的名称。

```js
const getType = v =>
  (v === undefined ? 'undefined' : v === null ? 'null' : v.constructor.name);
```

```js
getType(new Set([1, 2, 3])); // 'Set'
```
