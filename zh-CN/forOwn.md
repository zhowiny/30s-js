---
title: 遍历对象自己的属性(Iterate over object's own properties)
tags: object
expertise: intermediate
cover: blog_images/blank-card.jpg
firstSeen: 2018-01-18T16:45:56+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 遍历对象的所有自己的属性，为每个属性运行回调。
> Iterates over all own properties of an object, running a callback for each one.

- 使用 `Object.keys()` 获取对象的所有属性。
- 使用 `Array.prototype.forEach()` 为每个键值对运行提供的函数。
- 回调接收三个参数 - 值、键和对象。

```js
const forOwn = (obj, fn) =>
  Object.keys(obj).forEach(key => fn(obj[key], key, obj));
```

```js
forOwn({ foo: 'bar', a: 1 }, v => console.log(v)); // 'bar', 1
```
