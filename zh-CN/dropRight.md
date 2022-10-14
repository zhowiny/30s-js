---
title: 从右侧删除数组元素(Drop list elements from the right)
tags: array
expertise: beginner
cover: blog_images/messy-papers.jpg
firstSeen: 2017-12-19T12:06:47+02:00
lastUpdated: 2020-11-01T20:50:57+02:00
---

# 创建一个新数组，其中从右侧删除了 `n` 个元素。
> Creates a new array with `n` elements removed from the right.

- 使用 `Array.prototype.slice()` 从右侧删除指定数量的元素。
- 省略最后一个参数 `n` 以使用默认值 `1`。

```js
const dropRight = (arr, n = 1) => arr.slice(0, -n);
```

```js
dropRight([1, 2, 3]); // [1, 2]
dropRight([1, 2, 3], 2); // [1]
dropRight([1, 2, 3], 42); // []
```
