---
title: 合并排序数组(Merge sorted arrays)
tags: array
expertise: intermediate
author: maciv
cover: blog_images/digital-nomad-6.jpg
firstSeen: 2020-12-27T22:55:37+02:00
lastUpdated: 2020-12-27T22:55:37+02:00
---

# 将两个排序的数组合并为一个。
> Merges two sorted arrays into one.

- 使用扩展运算符 (`...`) 来克隆两个给定的数组。
- 使用 `Array.from()` 根据给定的数组创建一个适当长度的数组。
- 使用 `Array.prototype.shift()` 从克隆数组的删除元素中填充新创建的数组。

```js
const mergeSortedArrays = (a, b) => {
  const _a = [...a],
    _b = [...b];
  return Array.from({ length: _a.length + _b.length }, () => {
    if (!_a.length) return _b.shift();
    else if (!_b.length) return _a.shift();
    else return _a[0] > _b[0] ? _b.shift() : _a.shift();
  });
};
```

```js
mergeSortedArrays([1, 4, 5], [2, 3, 6]); // [1, 2, 3, 4, 5, 6]
```
