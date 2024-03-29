---
title: 排序数组中的最后插入索引(Last insertion index in sorted array)
tags: array
expertise: intermediate
cover: blog_images/rocky-beach-3.jpg
firstSeen: 2018-01-24T13:16:47+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 查找应将值插入数组以保持其排序顺序的最高索引。
> Finds the highest index at which a value should be inserted into an array in order to maintain its sort order.

- 松散地检查数组是否按降序排序。
- 使用 `Array.prototype.reverse()` 和 `Array.prototype.findIndex()` 找到应该插入元素的适当的最后一个索引。

```js
const sortedLastIndex = (arr, n) => {
  const isDescending = arr[0] > arr[arr.length - 1];
  const index = arr
    .reverse()
    .findIndex(el => (isDescending ? n <= el : n >= el));
  return index === -1 ? 0 : arr.length - index;
};
```

```js
sortedLastIndex([10, 20, 30, 30, 40], 30); // 4
```
