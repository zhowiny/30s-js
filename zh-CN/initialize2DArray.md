---
title: 初始化二维数组(Initialize 2D array)
tags: array
expertise: intermediate
cover: blog_images/cloudy-rock-formation.jpg
firstSeen: 2017-12-19T23:38:18+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 初始化给定宽度和高度和值的二维数组。
> Initializes a 2D array of given width and height and value.

- 使用 `Array.from()` 和 `Array.prototype.map()` 生成 `h` 行，其中每个行都是大小为 `w` 的新数组。
- 使用 `Array.prototype.fill()` 初始化所有值为 `val` 的项目。
- 省略最后一个参数 `val`，以使用默认值 `null`。

```js
const initialize2DArray = (w, h, val = null) =>
  Array.from({ length: h }).map(() => Array.from({ length: w }).fill(val));
```

```js
initialize2DArray(2, 2, 0); // [[0, 0], [0, 0]]
```
