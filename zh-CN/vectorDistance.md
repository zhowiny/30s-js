---
title: 向量的距离(Vector distance)
tags: math,algorithm
expertise: beginner
cover: blog_images/orange-coffee-3.jpg
firstSeen: 2019-02-23T19:13:48+02:00
lastUpdated: 2020-12-28T13:49:24+02:00
---

### 计算两个向量之间的距离。
> Calculates the distance between two vectors.

- 使用 `Array.prototype.reduce()`、`Math.pow()` 和 `Math.sqrt()` 计算两个向量之间的欧几里得距离。

```js
const vectorDistance = (x, y) =>
  Math.sqrt(x.reduce((acc, val, i) => acc + Math.pow(val - y[i], 2), 0));
```

```js
vectorDistance([10, 0, 5], [20, 0, 10]); // 11.180339887498949
```
