---
title: 选择排序(Selection sort)
tags: algorithm,array
expertise: intermediate
author: chalarangelo
cover: blog_images/violin.jpg
firstSeen: 2020-12-27T22:22:44+02:00
lastUpdated: 2021-10-13T19:29:39+02:00
---

### 使用选择排序算法对数字数组进行排序。
> Sorts an array of numbers, using the selection sort algorithm.

- 使用扩展运算符 (`...`) 克隆原始数组 `arr`。
- 使用 `for` 循环遍历数组中的元素。
- 使用 `Array.prototype.slice()` 和 `Array.prototype.reduce()` 查找当前索引右侧子数组中最小元素的索引。 如有必要，请执行交换。

```js
const selectionSort = arr => {
  const a = [...arr];
  for (let i = 0; i < a.length; i++) {
    const min = a
      .slice(i + 1)
      .reduce((acc, val, j) => (val < a[acc] ? j + i + 1 : acc), i);
    if (min !== i) [a[i], a[min]] = [a[min], a[i]];
  }
  return a;
};
```

```js
selectionSort([5, 1, 4, 2, 3]); // [1, 2, 3, 4, 5]
```
