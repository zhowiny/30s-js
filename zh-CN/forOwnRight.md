---
title: 反向迭代对象自身的属性(Iterate over object's own properties in reverse)
tags: object
expertise: intermediate
cover: blog_images/sea-view.jpg
firstSeen: 2018-01-18T16:45:56+02:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 反向迭代对象的所有自身属性，为每个属性运行回调。
> Iterates over all own properties of an object in reverse, running a callback for each one.

- 使用 `Object.keys()` 获取对象的所有属性，`Array.prototype.reverse()` 反转它们的顺序。
- 使用 `Array.prototype.forEach()` 为每个键值对运行提供的函数。
- 回调接收三个参数 - 值、键和对象。

```js
const forOwnRight = (obj, fn) =>
  Object.keys(obj)
    .reverse()
    .forEach(key => fn(obj[key], key, obj));
```

```js
forOwnRight({ foo: 'bar', a: 1 }, v => console.log(v)); // 1, 'bar'
```
