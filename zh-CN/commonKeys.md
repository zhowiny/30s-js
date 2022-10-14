---
title: 公共key(Common keys)
tags: object
expertise: intermediate
author: chalarangelo
cover: blog_images/symmetry-cloudy-mountain.jpg
firstSeen: 2022-04-23T05:00:00-04:00
---

# 找到两个对象之间的共同键。
> Finds the common keys between two objects.

- 使用`object.keys()`以获取第一个对象的键。
- 使用`object.prototype.hasownproperty()`以检查第二个对象是否具有第一个对象中的键。
- 使用`array.prototype.filter()`来过滤两个对象中不在两个对象中的键。

```js
const commonKeys = (obj1, obj2) =>
  Object.keys(obj1).filter(key => obj2.hasOwnProperty(key));
```

```js
commonKeys({ a: 1, b: 2 }, { a: 2, c: 1 }); // ['a']
```
