---
title: 排序数组中的插入索引(Insertion index in sorted array)
tags: array,math
expertise: intermediate
cover: blog_images/apples.jpg
firstSeen: 2017-12-31T16:39:06+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 查找应将值插入数组以保持其排序顺序的最低索引。
> Finds the lowest index at which a value should be inserted into an array in order to maintain its sorting order.

- 松散地检查数组是否按降序排序。
- 使用 `Array.prototype.findIndex()` 找到应该插入元素的适当索引。

```js
const sortedIndex = (arr, n) => {
  const isDescending = arr[0] > arr[arr.length - 1];
  const index = arr.findIndex(el => (isDescending ? n >= el : n <= el));
  return index === -1 ? arr.length : index;
};
```

```js
sortedIndex([5, 3, 2, 1], 4); // 1
sortedIndex([30, 50], 40); // 1
```
