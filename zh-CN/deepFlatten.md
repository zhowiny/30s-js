---
title: 深度展开数组(Deep flatten array)
tags: array,recursion
expertise: intermediate
cover: blog_images/digital-nomad-4.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 深度扁平化数组。

> Deep flattens an array.

- 使用递归。
- 将 `Array.prototype.concat()` 与空数组 (`[]`) 和扩展运算符 (`...`) 一起使用以展平数组。
- 递归地展平作为数组的每个元素。

```js
const deepFlatten = arr =>
  [].concat(...arr.map(v => (Array.isArray(v) ? deepFlatten(v) : v)));
```

```js
deepFlatten([1, [2], [[3], 4], 5]); // [1, 2, 3, 4, 5]
```
