---
title: 向量之间的角度(Vector angle)
tags: math
expertise: beginner
cover: blog_images/avocado-slices.jpg
firstSeen: 2019-12-16T16:43:13+02:00
lastUpdated: 2021-01-08T00:23:44+02:00
---

### 计算两个向量之间的角度 (theta)。
> Calculates the angle (theta) between two vectors.

- 使用 `Array.prototype.reduce()`、`Math.pow()` 和 `Math.sqrt()` 计算每个向量的大小和两个向量的标量积。
- 使用 `Math.acos()` 计算反余弦并获得 theta 值。
- [向量(维基百科)](https://zh.wikipedia.org/zh-cn/%E5%90%91%E9%87%8F)

```js
const vectorAngle = (x, y) => {
  let mX = Math.sqrt(x.reduce((acc, n) => acc + Math.pow(n, 2), 0));
  let mY = Math.sqrt(y.reduce((acc, n) => acc + Math.pow(n, 2), 0));
  return Math.acos(x.reduce((acc, n, i) => acc + n * y[i], 0) / (mX * mY));
};
```

```js
vectorAngle([3, 4], [4, 3]); // 0.283794109208328
```

