---
title: 中点(Midpoint)
tags: math
expertise: beginner
cover: blog_images/curve.jpg
firstSeen: 2018-11-15T17:49:04+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 计算两对 (x,y) 点之间的中点。
> Calculates the midpoint between two pairs of (x,y) points.

- 解构数组以获得`x1`、`y1`、`x2`和`y2`。
- 通过将两个端点的总和除以 `2` 来计算每个维度的中点。

```js
const midpoint = ([x1, y1], [x2, y2]) => [(x1 + x2) / 2, (y1 + y2) / 2];
```

```js
midpoint([2, 2], [4, 4]); // [3, 3]
midpoint([4, 4], [6, 6]); // [5, 5]
midpoint([1, 3], [2, 4]); // [1.5, 3.5]
```
