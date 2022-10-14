---
title: 为对象属性分配默认值(Assign default values for object properties)
tags: object
expertise: intermediate
cover: blog_images/boats.jpg
firstSeen: 2018-01-19T13:51:05+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 为对象中`undefined`的所有属性分配默认值。
> Assigns default values for all properties in an object that are `undefined`.

- 使用 `Object.assign()` 创建一个新的空对象并复制原始对象以保持键顺序。
- 使用 `Array.prototype.reverse()` 和扩展运算符 (`...`) 从左到右组合默认值。
- 最后，再次使用 `obj` 覆盖原来有值的属性。

```js
const defaults = (obj, ...defs) =>
  Object.assign({}, obj, ...defs.reverse(), obj);
```

```js
defaults({ a: 1 }, { b: 2 }, { b: 6 }, { a: 3 }); // { a: 1, b: 2 }
```
