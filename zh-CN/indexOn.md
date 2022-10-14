---
title: 根据`key`从数组创建对象(Array to object based on key)
tags: array,object
expertise: intermediate
author: chalarangelo
cover: blog_images/lavender-shelf.jpg
firstSeen: 2021-06-27T05:00:00-04:00
---

# 从数组中创建一个对象，使用指定的键并将其从每个值中排除。
> Creates an object from an array, using the specified key and excluding it from each value.

- 使用 `Array.prototype.reduce()` 从 `arr` 创建一个对象。
- 使用对象解构来获取给定 `key` 和关联的 `data` 的值，并将键值对添加到对象中。

```js
const indexOn = (arr, key) =>
  arr.reduce((obj, v) => {
    const { [key]: id, ...data } = v;
    obj[id] = data;
    return obj;
  }, {});
```

```js
indexOn([
  { id: 10, name: 'apple' },
  { id: 20, name: 'orange' }
], 'id');
// { '10': { name: 'apple' }, '20': { name: 'orange' } }
```
