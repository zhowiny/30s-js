---
title: 值是对象(Value is object)
tags: type,object
expertise: beginner
cover: blog_images/flower-portrait-9.jpg
firstSeen: 2018-01-11T12:24:06+02:00
lastUpdated: 2021-01-08T00:23:44+02:00
---

### 检查传递的值是否为对象。
> Checks if the passed value is an object or not.

- 使用 `Object` 构造函数为给定值创建对象包装器。
- 如果值为 `null` 或 `undefined`，则创建并返回一个空对象。
- 否则，返回与给定值对应的类型的对象。

```js
const isObject = obj => obj === Object(obj);
```

```js
isObject([1, 2, 3, 4]); // true
isObject([]); // true
isObject(['Hello!']); // true
isObject({ a: 1 }); // true
isObject({}); // true
isObject(true); // false
```
