---
title: 将数组拆分为 n 个块(Split array into n chunks)
tags: array
expertise: intermediate
author: chalarangelo
cover: blog_images/dark-leaves-2.jpg
firstSeen: 2020-05-04T13:00:46+03:00
lastUpdated: 2020-11-03T21:46:13+02:00
---
# 将一个数组分块成 `n` 个较小的数组。
> Chunks an array into `n` smaller arrays.

- 使用 `Math.ceil()` 和 `Array.prototype.length` 获取每个块的大小。
- 使用 `Array.from()` 创建一个大小为 `n` 的新数组。
- 使用 `Array.prototype.slice()` 将新数组的每个元素映射到长度为 `size` 的块。
- 如果原始数组不能被平均分割，最终的块将包含剩余的元素。

```js
const chunkIntoN = (arr, n) => {
  const size = Math.ceil(arr.length / n);
  return Array.from({ length: n }, (v, i) =>
    arr.slice(i * size, i * size + size)
  );
}
```

```js
chunkIntoN([1, 2, 3, 4, 5, 6, 7], 4); // [[1, 2], [3, 4], [5, 6], [7]]
```
