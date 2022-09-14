---
title: 最大子数列(Maximum subarray)
tags: algorithm,math,array
author: chalarangelo
cover: blog_images/work-hard-computer.jpg
expertise: intermediate
firstSeen: 2022-09-07T05:00:00-04:00
---

### 查找数字数组中总和最大的连续子数组。
> Finds a contiguous subarray with the largest sum within an array of numbers.

- 使用贪心方法来跟踪当前的 `sum` 和当前的最大值 `maxSum`。 将 `maxSum` 设置为 `-Infinity` 以确保如果所有值都是负数，则返回最大的负值。
- 定义变量以跟踪最大开始索引`sMax`、最大结束索引`eMax`和当前开始索引`s`。
- 使用 `Array.prototype.forEach()` 迭代值并将当前值添加到 `sum`。
- 如果当前的 `sum` 大于 `maxSum`，则更新索引值和 `maxSum`。
- 如果 `sum` 低于 `0`，将其重置为 `0` 并将 `s` 的值更新为下一个索引。
- 使用 `Array.prototype.slice()` 返回索引变量指示的子数组。

```js
const maxSubarray = (...arr) => {
  let maxSum = -Infinity,
    sum = 0;
  let sMax = 0,
    eMax = arr.length - 1,
    s = 0;

  arr.forEach((n, i) => {
    sum += n;
    if (maxSum < sum) {
      maxSum = sum;
      sMax = s;
      eMax = i;
    }

    if (sum < 0) {
      sum = 0;
      s = i + 1;
    }
  });

  return arr.slice(sMax, eMax + 1);
};

```

```js
maxSubarray(-2, 1, -3, 4, -1, 2, 1, -5, 4); // [4, -1, 2, 1]
```
