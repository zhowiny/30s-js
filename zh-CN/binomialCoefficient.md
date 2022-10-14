---
title: 二项式系数(Binomial coefficient)
tags: math,algorithm
expertise: beginner
cover: blog_images/blue-red-mountain.jpg
firstSeen: 2018-02-14T12:34:02+02:00
lastUpdated: 2020-12-28T13:49:24+02:00
---

# 计算从 `n` 个项目中选择 `k` 个项目而不重复且无顺序的方式数。
> Calculates the number of ways to choose `k` items from `n` items without repetition and without order.

- 使用 `Number.isNaN()` 检查两个值中的任何一个是否为 `NaN`。
- 检查 `k` 是否小于 `0`、大于或等于 `n`、等于 `1` 或 `n - 1` 并返回适当的结果。
- 检查 `n - k` 是否小于 `k` 并相应地切换它们的值。
- 从 `2` 到 `k` 循环并计算二项式系数。
- 使用 `Math.round()` 来解释计算中的舍入误差。

```js
const binomialCoefficient = (n, k) => {
  if (Number.isNaN(n) || Number.isNaN(k)) return NaN;
  if (k < 0 || k > n) return 0;
  if (k === 0 || k === n) return 1;
  if (k === 1 || k === n - 1) return n;
  if (n - k < k) k = n - k;
  let res = n;
  for (let j = 2; j <= k; j++) res *= (n - j + 1) / j;
  return Math.round(res);
};
```

```js
binomialCoefficient(8, 2); // 28
```


> [二项式系数(维基百科)](https://zh.wikipedia.org/zh-cn/%E4%BA%8C%E9%A0%85%E5%BC%8F%E4%BF%82%E6%95%B8)
>
> [二项式系数(百度百科)](https://baike.baidu.com/item/%E4%BA%8C%E9%A1%B9%E5%BC%8F%E7%B3%BB%E6%95%B0/6763242)
>
> [二项式定理](https://www.shuxuele.com/algebra/binomial-theorem.html)
