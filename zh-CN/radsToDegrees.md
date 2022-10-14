---
title: 弧度转度数(Radians to degrees)
tags: math
expertise: beginner
cover: blog_images/flower-portrait-6.jpg
firstSeen: 2018-02-14T12:24:50+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 将角度从弧度转换为度。
> Converts an angle from radians to degrees.

- 使用 `Math.PI` 和弧度到度数公式将角度从弧度转换为度数。

```js
const radsToDegrees = rad => (rad * 180.0) / Math.PI;
```

```js
radsToDegrees(Math.PI / 2); // 90
```
