---
title: 浅克隆对象(Shallow clone object)
tags: object
expertise: beginner
cover: blog_images/pagodas.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

### 创建一个浅层克隆对象。
> Creates a shallow clone of an object.

- 使用 `Object.assign()` 和一个空对象 (`{}`) 创建原始的浅克隆。

```js
const shallowClone = obj => Object.assign({}, obj);
```

```js
const a = { x: true, y: 1 };
const b = shallowClone(a); // a !== b
```
