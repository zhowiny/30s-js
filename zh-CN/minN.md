---
title: N 个最小元素(N min elements)
tags: array,math
expertise: intermediate
cover: blog_images/digital-nomad-8.jpg
firstSeen: 2018-01-03T05:18:29+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

# 从提供的数组中返回 `n` 个最小元素。
> Returns the `n` minimum elements from the provided array.

- 使用 `Array.prototype.sort()` 结合扩展运算符 (`...`) 创建数组的浅克隆并按升序对其进行排序。
- 使用 `Array.prototype.slice()` 获取指定数量的元素。
- 省略第二个参数 `n` 以获取单元素数组。
- 如果 `n` 大于或等于提供的数组的长度，则返回原始数组（按升序排序）。

```js
const minN = (arr, n = 1) => [...arr].sort((a, b) => a - b).slice(0, n);
```

```js
minN([1, 2, 3]); // [1]
minN([1, 2, 3], 2); // [1, 2]
```
