---
title: 根据函数获取排序数组中的插入索引(Insertion index in sorted array based on function)
tags: array,math
expertise: intermediate
cover: blog_images/digital-nomad-15.jpg
firstSeen: 2018-01-26T13:39:09+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 根据提供的迭代器函数，查找应将值插入数组以保持其排序顺序的最低索引。
> Finds the lowest index at which a value should be inserted into an array in order to maintain its sorting order, based on the provided iterator function.

- 松散地检查数组是否按降序排序。
- 使用 `Array.prototype.findIndex()` 根据迭代器函数 `fn` 找到应该插入元素的适当索引。

```js
const sortedIndexBy = (arr, n, fn) => {
  const isDescending = fn(arr[0]) > fn(arr[arr.length - 1]);
  const val = fn(n);
  const index = arr.findIndex(el =>
    isDescending ? val >= fn(el) : val <= fn(el)
  );
  return index === -1 ? arr.length : index;
};
```

```js
sortedIndexBy([{ x: 4 }, { x: 5 }], { x: 4 }, o => o.x); // 0
```
