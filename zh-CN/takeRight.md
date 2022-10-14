---
title: 从末尾取出数组元素(Remove list elements from the end)
tags: array
expertise: intermediate
cover: blog_images/interior-7.jpg
firstSeen: 2017-12-15T02:00:10+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 从末端取出 `n` 个元素创建到数组。
> Creates an array with `n` elements removed from the end.

- 使用 `Array.prototype.slice()` 创建一个数组切片，其中包含从末尾获取的 `n` 个元素。

```js
const takeRight = (arr, n = 1) => arr.slice(arr.length - n, arr.length);
```

```js
takeRight([1, 2, 3], 2); // [ 2, 3 ]
takeRight([1, 2, 3]); // [3]
```
