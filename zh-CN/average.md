---
title: 数字的平均值(Average of numbers)
tags: math,array
expertise: beginner
cover: blog_images/interior-8.jpg
firstSeen: 2017-12-29T13:29:49+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 计算两个或多个数字的平均值。
> Calculates the average of two or more numbers.

- 使用 `Array.prototype.reduce()` 将每个值添加到累加器，初始值为 `0`。
- 将结果数组除以其长度。

```js
const average = (...nums) =>
  nums.reduce((acc, val) => acc + val, 0) / nums.length;
```

```js
average(...[1, 2, 3]); // 2
average(1, 2, 3); // 2
```
