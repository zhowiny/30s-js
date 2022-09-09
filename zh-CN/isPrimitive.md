---
title: 值是原始类型(Number is primitive)
tags: type
expertise: intermediate
cover: blog_images/flower-camera.jpg
firstSeen: 2017-12-31T12:48:13+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 检查传递的值是否是原始的。
> Checks if the passed value is primitive or not.

- 从 `val` 创建一个对象并将其与 `val` 进行比较以确定传递的值是否是原始的（即不等于创建的对象）。

```js
const isPrimitive = val => Object(val) !== val;
```

```js
isPrimitive(null); // true
isPrimitive(undefined); // true
isPrimitive(50); // true
isPrimitive('Hello!'); // true
isPrimitive(false); // true
isPrimitive(Symbol()); // true
isPrimitive([]); // false
isPrimitive({}); // false
```
