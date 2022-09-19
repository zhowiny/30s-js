---
title: 数组排名(Array ranking)
tags: array,math
expertise: intermediate
author: chalarangelo
cover: blog_images/eagle.jpg
firstSeen: 2022-04-13T05:00:00-04:00
---

### 根据比较器函数计算数组的排名。
> Calculates the ranking of an array based on a comparator function.

根据比较器函数计算数组的排名。- 使用 `Array.prototype.map()` 和 `Array.prototype.filter()` 使用提供的比较器函数将每个元素映射到排名。

```js
const ranking = (arr, compFn) =>
  arr.map(a => arr.filter(b => compFn(a, b)).length + 1);
```

```js
ranking([8, 6, 9, 5], (a, b) => a < b);
// [2, 3, 1, 4]
ranking(['c', 'a', 'b', 'd'], (a, b) => a.localeCompare(b) > 0);
// [3, 1, 2, 4]
```
