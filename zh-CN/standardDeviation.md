---
title: 标准差(均方差)(Standard deviation)
tags: math,array
expertise: intermediate
cover: blog_images/interior-16.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 计算数字数组的标准差。
> Calculates the standard deviation of an array of numbers.

- 使用`Array.prototype.reduce()`计算值的均值、方差和方差之和，并确定标准差。
- 省略第二个参数，`usePopulation`，以获取样本标准差，或将其设置为 `true` 以获取总体标准差。

```js
const standardDeviation = (arr, usePopulation = false) => {
  const mean = arr.reduce((acc, val) => acc + val, 0) / arr.length;
  return Math.sqrt(
    arr
      .reduce((acc, val) => acc.concat((val - mean) ** 2), [])
      .reduce((acc, val) => acc + val, 0) /
      (arr.length - (usePopulation ? 0 : 1))
  );
};
```

```js
standardDeviation([10, 2, 38, 23, 38, 23, 21]); // 13.284434142114991 (sample)
standardDeviation([10, 2, 38, 23, 38, 23, 21], true);
// 12.29899614287479 (population)
```
