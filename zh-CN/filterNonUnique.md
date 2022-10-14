---
title: 过滤非唯一数组值(Filter non-unique array values)
tags: array
expertise: beginner
cover: blog_images/digital-nomad-10.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-11-02T19:40:45+02:00
---

# 创建一个过滤掉非唯一值的数组。
> Creates an array with the non-unique values filtered out.

- 使用 `Set` 构造函数和扩展运算符 (`...`) 在 `arr` 中创建唯一值数组。
- 使用 `Array.prototype.filter()` 创建一个仅包含唯一值的数组。

```js
const filterNonUnique = arr =>
  [...new Set(arr)].filter(i => arr.indexOf(i) === arr.lastIndexOf(i));
```

```js
filterNonUnique([1, 2, 2, 3, 4, 4, 5]); // [1, 3, 5]
```
