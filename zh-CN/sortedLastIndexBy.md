---
title: 根据函数获取排序数组中的最后插入索引(Last insertion index in sorted array based on function)
tags: array
expertise: intermediate
cover: blog_images/hard-disk.jpg
firstSeen: 2018-01-26T13:39:09+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 根据提供的迭代器函数，查找应将值插入数组以保持其排序顺序的最高索引。
> Finds the highest index at which a value should be inserted into an array in order to maintain its sort order, based on a provided iterator function.

- 松散地检查数组是否按降序排序。
- 使用 `Array.prototype.map()` 将迭代器函数应用于数组的所有元素。
- 根据提供的迭代器函数，使用 `Array.prototype.reverse()` 和 `Array.prototype.findIndex()` 找到应该插入元素的适当最后索引。

```js
const sortedLastIndexBy = (arr, n, fn) => {
  const isDescending = fn(arr[0]) > fn(arr[arr.length - 1]);
  const val = fn(n);
  const index = arr
    .map(fn)
    .reverse()
    .findIndex(el => (isDescending ? val <= el : val >= el));
  return index === -1 ? 0 : arr.length - index;
};
```

```js
sortedLastIndexBy([{ x: 4 }, { x: 5 }], { x: 4 }, o => o.x); // 1
```
