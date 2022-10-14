---
title: 取出数组元素(Remove list elements)
tags: array
expertise: beginner
cover: blog_images/interior-9.jpg
firstSeen: 2017-12-14T11:35:14+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 创建一个数组，其中从开头取出了 `n` 个元素。
> Creates an array with `n` elements removed from the beginning.

- 使用 `Array.prototype.slice()` 创建一个数组切片，其中包含从开头获取的 `n` 个元素。

```js
const take = (arr, n = 1) => arr.slice(0, n);
```

```js
take([1, 2, 3], 5); // [1, 2, 3]
take([1, 2, 3], 0); // []
```
