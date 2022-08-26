---
title: 冒泡排序(Bubble sort)
tags: algorithm,array
expertise: beginner
author: maciv
cover: blog_images/budapest-palace.jpg
firstSeen: 2020-12-27T21:20:31+02:00
lastUpdated: 2020-12-29T12:18:58+02:00
---

### 使用冒泡排序算法对数字数组进行排序。
> Sorts an array of numbers, using the bubble sort algorithm.

- 声明一个变量，`swapped`，指示在当前迭代期间是否有任何值被交换。
- 使用扩展运算符 (`...`) 克隆原始数组 `arr`。
- 使用 `for` 循环遍历克隆数组的元素，在最后一个元素之前终止。
- 使用嵌套的 `for` 循环遍历 `0` 和 `i` 之间的数组段，交换任何相邻的乱序元素并将 `swapped` 设置为 `true`。
- 如果 `swapped` 在一次迭代后为 `false`，则不需要进行更多更改，因此返回克隆的数组。

```js
const bubbleSort = arr => {
  let swapped = false;
  const a = [...arr];
  for (let i = 1; i < a.length; i++) {
    swapped = false;
    for (let j = 0; j < a.length - i; j++) {
      if (a[j + 1] < a[j]) {
        [a[j], a[j + 1]] = [a[j + 1], a[j]];
        swapped = true;
      }
    }
    if (!swapped) return a;
  }
  return a;
};
```

```js
bubbleSort([2, 1, 4, 3]); // [1, 2, 3, 4]
```
