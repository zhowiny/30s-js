---
title: 堆排序(Heap sort)
tags: algorithm,array,recursion
expertise: advanced
author: chalarangelo
cover: blog_images/building-blocks.jpg
firstSeen: 2020-12-28T22:48:09+02:00
lastUpdated: 2020-12-28T22:48:09+02:00
---

# 使用堆排序算法对数字数组进行排序。
> Sorts an array of numbers, using the heapsort algorithm.

- 使用递归。
- 使用扩展运算符 (`...`) 克隆原始数组 `arr`。
- 使用闭包来声明一个变量 `l` 和一个函数 `heapify`。
- 使用 `for` 循环和 `Math.floor()` 结合 `heapify` 从数组创建最大堆。
- 使用 `for` 循环重复缩小考虑范围，使用 `heapify` 并根据需要交换值以对克隆数组进行排序。

```js
const heapsort = arr => {
  const a = [...arr];
  let l = a.length;

  const heapify = (a, i) => {
    const left = 2 * i + 1;
    const right = 2 * i + 2;
    let max = i;
    if (left < l && a[left] > a[max]) max = left;
    if (right < l && a[right] > a[max]) max = right;
    if (max !== i) {
      [a[max], a[i]] = [a[i], a[max]];
      heapify(a, max);
    }
  };

  for (let i = Math.floor(l / 2); i >= 0; i -= 1) heapify(a, i);
  for (i = a.length - 1; i > 0; i--) {
    [a[0], a[i]] = [a[i], a[0]];
    l--;
    heapify(a, 0);
  }
  return a;
};
```

```js
heapsort([6, 3, 4, 1]); // [1, 3, 4, 6]
```
