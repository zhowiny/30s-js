---
title: 两点之间的距离(Distance between two points)
tags: math,algorithm
expertise: beginner
cover: blog_images/measuring.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-12-28T13:49:24+02:00
---

### 计算两点之间的距离。
> Calculates the distance between two points.

- 使用 `Math.hypot()` 计算两点之间的欧几里得距离。

```js
const distance = (x0, y0, x1, y1) => Math.hypot(x1 - x0, y1 - y0);
```

```js
distance(1, 1, 2, 3); // ~2.2361
```
