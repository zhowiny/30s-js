---
title: 分割成块(Split into chunks)
tags: array
expertise: intermediate
cover: blog_images/filter-coffee-pot.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-11-03T21:35:12+02:00
---

# 将数组分块为指定大小的较小数组。
> Chunks an array into smaller arrays of a specified size.

- 使用 `Array.from()` 创建一个新数组，该数组适合将要生成的块的数量。
- 使用 `Array.prototype.slice()` 将新数组的每个元素映射到长度为 `size` 的块。
- 如果原始数组不能被平均分割，最终的块将包含剩余的元素。

```js
const chunk = (arr, size) =>
  Array.from({ length: Math.ceil(arr.length / size) }, (v, i) =>
    arr.slice(i * size, i * size + size)
  );
```

```js
chunk([1, 2, 3, 4, 5], 2); // [[1, 2], [3, 4], [5]]
```
