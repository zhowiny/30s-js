---
title: 反向执行每个数组元素的函数(Execute function for each array element in reverse)
tags: array
expertise: intermediate
cover: blog_images/interior-6.jpg
firstSeen: 2018-01-09T01:38:50+02:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 从数组的最后一个元素开始，为每个数组元素执行一次提供的函数。
> Executes a provided function once for each array element, starting from the array's last element.

- 使用 `Array.prototype.slice()` 克隆给定的数组并使用 `Array.prototype.reverse()` 反转它。
- 使用 `Array.prototype.forEach()` 来迭代反向数组。

```js
const forEachRight = (arr, callback) =>
  arr
    .slice()
    .reverse()
    .forEach(callback);
```

```js
forEachRight([1, 2, 3, 4], val => console.log(val)); // '4', '3', '2', '1'
```
