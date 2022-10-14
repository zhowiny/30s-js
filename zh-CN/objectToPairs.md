---
title: 对象转为键值对数组(Object to pairs)
tags: object,array
expertise: beginner
author: chalarangelo
cover: blog_images/interior-5.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 从一个对象创建一个键值对数组。
> Creates an array of key-value pair arrays from an object.

- 使用 `Object.entries()` 从给定对象获取键值对数组的数组。

```js
const objectToPairs = obj => Object.entries(obj);
```

```js
objectToPairs({ a: 1, b: 2 }); // [ ['a', 1], ['b', 2] ]
```
