---
title: 欧几里得距离(Euclidean distance)
tags: math,algorithm
expertise: intermediate
author: chalarangelo
cover: blog_images/ancient-greek-building.jpg
firstSeen: 2020-12-28T13:41:19+02:00
lastUpdated: 2020-12-28T13:41:19+02:00
---

### 计算任意维数中两点之间的距离。
> Calculates the distance between two points in any number of dimensions.

- 使用 `Object.keys()` 和 `Array.prototype.map()` 将每个坐标映射到两点之间的差异。
- 使用 `Math.hypot()` 计算两点之间的欧几里得距离。

```js
const euclideanDistance = (a, b) =>
  Math.hypot(...Object.keys(a).map(k => b[k] - a[k]));
```

```js
euclideanDistance([1, 1], [2, 3]); // ~2.2361
euclideanDistance([1, 1, 1], [2, 3, 2]); // ~2.4495
```
