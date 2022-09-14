---
title: 将Map转换为对象(Convert Map to object)
shortTitle: Map to object
tags: object
expertise: intermediate
author: chalarangelo
cover: blog_images/succulent-1.jpg
firstSeen: 2022-06-16T05:00:00-04:00
---

### 将 `Map` 转换为对象。
> Converts a `Map` to an object.

- 使用 `Map.prototype.entries()` 将 `Map` 转换为键值对数组。
- 使用 `Object.fromEntries()` 将数组转换为对象。

```js
const mapToObject = map => Object.fromEntries(map.entries());
```

```js
mapToObject(new Map([['a', 1], ['b', 2]])); // {a: 1, b: 2}
```
