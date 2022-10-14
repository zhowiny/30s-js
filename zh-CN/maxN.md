---
title: 最大N个元素(N max elements)
tags: array,math
expertise: intermediate
cover: blog_images/digital-nomad-15.jpg
firstSeen: 2018-01-03T05:18:29+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

# 从提供的数组中返回 `n` 个最大元素。
> Returns the `n` maximum elements from the provided array.

- 使用 `Array.prototype.sort()` 和扩展运算符 (`...`) 来创建数组的浅克隆并按降序对其进行排序。
- 使用 `Array.prototype.slice()` 获取指定数量的元素。
- 省略第二个参数 `n` 以获取单元素数组。
- 如果 `n` 大于或等于提供的数组的长度，则返回原始数组（按降序排序）。

```js
const maxN = (arr, n = 1) => [...arr].sort((a, b) => b - a).slice(0, n);
```

```js
maxN([1, 2, 3]); // [3]
maxN([1, 2, 3], 2); // [3, 2]
```
