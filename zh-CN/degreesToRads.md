---
title: 角度转弧度(Degrees to radians)
tags: math
expertise: beginner
cover: blog_images/blue-flower.jpg
firstSeen: 2018-02-14T12:24:50+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 将角度从度数转换为弧度。
> Converts an angle from degrees to radians.

- 使用 `Math.PI` 和度数到弧度公式将角度从度数转换为弧度。

```js
const degreesToRads = deg => (deg * Math.PI) / 180.0;
```

```js
degreesToRads(90.0); // ~1.5708
```
