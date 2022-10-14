---
title: 连续值数组(Array of successive values)
tags: array
expertise: intermediate
cover: blog_images/laptop-view.jpg
firstSeen: 2018-01-24T16:38:08+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 对累加器和数组中的每个元素（从左到右）应用一个函数，返回一个连续减少值的数组。
> Applies a function against an accumulator and each element in the array (from left to right), returning an array of successively reduced values.

- 使用 `Array.prototype.reduce()` 将给定函数应用于给定数组，存储每个新结果。

```js
const reduceSuccessive = (arr, fn, acc) =>
  arr.reduce(
    (res, val, i, arr) => (res.push(fn(res.slice(-1)[0], val, i, arr)), res),
    [acc]
  );
```

```js
reduceSuccessive([1, 2, 3, 4, 5, 6], (acc, val) => acc + val, 0);
// [0, 1, 3, 6, 10, 15, 21]
```
