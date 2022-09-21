---
title: 加权平均值(Weighted average)
tags: math
expertise: intermediate
cover: blog_images/interior-12.jpg
firstSeen: 2020-10-04T00:38:33+03:00
lastUpdated: 2020-11-03T21:46:13+02:00
---

### 计算两个或多个数字的加权平均值。
> Calculates the weighted average of two or more numbers.

- 使用 `Array.prototype.reduce()` 创建值的加权总和和权重总和。
- 将它们相互除以得到加权平均值。

```js
const weightedAverage = (nums, weights) => {
  const [sum, weightSum] = weights.reduce(
    (acc, w, i) => {
      acc[0] = acc[0] + nums[i] * w;
      acc[1] = acc[1] + w;
      return acc;
    },
    [0, 0]
  );
  return sum / weightSum;
};
```

```js
weightedAverage([1, 2, 3], [0.6, 0.2, 0.3]); // 1.72727
```
