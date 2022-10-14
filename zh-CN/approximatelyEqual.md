---
title: 数字近似相等(Approximately number equality)
tags: math
expertise: beginner
cover: blog_images/engine.jpg
firstSeen: 2018-02-14T12:47:13+02:00
lastUpdated: 2020-11-01T20:50:57+02:00
---

# 检查两个数字是否大致相等。
> Checks if two numbers are approximately equal to each other.

- 使用 `Math.abs()` 将两个值的绝对差值与 `epsilon` 进行比较。
- 省略第三个参数 `epsilon` ，使用默认值 `0.001` 。

```js
const approximatelyEqual = (v1, v2, epsilon = 0.001) =>
  Math.abs(v1 - v2) < epsilon;
```

```js
approximatelyEqual(Math.PI / 2.0, 1.5708); // true
```
