---
title: 设备是否支持触摸事件(Device supports touch events)
tags: browser
expertise: beginner
author: chalarangelo
cover: blog_images/man-red-sunset.jpg
firstSeen: 2020-05-04T12:57:23+03:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 检查是否支持触摸事件。
> Checks if touch events are supported.

- 检查 `Window` 中是否存在 `'ontouchstart'` 。

```js
const supportsTouchEvents = () =>
  window && 'ontouchstart' in window;
```

```js
supportsTouchEvents(); // true
```
