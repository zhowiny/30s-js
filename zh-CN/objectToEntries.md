---
title: 对象转为键值对数组(Object to entries)
tags: object,array
expertise: beginner
author: chalarangelo
cover: blog_images/shapes.jpg
firstSeen: 2020-04-16T11:10:13+03:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 从一个对象创建一个键值对数组。
> Creates an array of key-value pair arrays from an object.

- 使用 `Object.keys()` 和 `Array.prototype.map()` 来迭代对象的键并生成具有键值对的数组。
- [`Object.entries()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/entries) 提供了类似的功能。

```js
const objectToEntries = obj => Object.keys(obj).map(k => [k, obj[k]]);
```

```js
objectToEntries({ a: 1, b: 2 }); // [ ['a', 1], ['b', 2] ]
```
