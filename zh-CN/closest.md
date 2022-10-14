---
title: 最接近的数字匹配(Closest numeric match)
tags: math,array
expertise: intermediate
author: chalarangelo
cover: blog_images/sparkles.jpg
firstSeen: 2022-03-30T05:00:00-04:00
---

# 从数组中查找最接近的数字。
> Finds the closest number from an array.

- 使用 `Array.prototype.reduce()` 扫描数组的所有元素。
- 使用 `Math.abs()` 比较每个元素与目标值的距离，存储最接近的匹配项。

```js
const closest = (arr, n) =>
  arr.reduce((acc, num) => (Math.abs(num - n) < Math.abs(acc - n) ? num : acc));
```

```js
closest([6, 1, 3, 7, 9], 5); // 6
```
