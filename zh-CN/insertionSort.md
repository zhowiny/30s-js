---
title: 插入排序(Insertion sort)
tags: algorithm,array
expertise: intermediate
author: chalarangelo
cover: blog_images/goat-wooden-cottage.jpg
firstSeen: 2020-12-28T21:53:53+02:00
lastUpdated: 2020-12-28T21:53:53+02:00
---

# 使用插入排序算法对数字数组进行排序。
> Sorts an array of numbers, using the insertion sort algorithm.

- 使用 `Array.prototype.reduce()` 迭代给定数组中的所有元素。
- 如果累加器的 `length` 为 `0`，则将当前元素添加到其中。
- 使用 `Array.prototype.some()` 迭代累加器中的结果，直到找到正确的位置。
- 使用 `Array.prototype.splice()` 将当前元素插入累加器。

```js
const insertionSort = arr =>
  arr.reduce((acc, x) => {
    if (!acc.length) return [x];
    acc.some((y, j) => {
      if (x <= y) {
        acc.splice(j, 0, x);
        return true;
      }
      if (x > y && j === acc.length - 1) {
        acc.splice(j + 1, 0, x);
        return true;
      }
      return false;
    });
    return acc;
  }, []);
```

```js
insertionSort([6, 3, 4, 1]); // [1, 3, 4, 6]
```
