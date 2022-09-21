---
title: 一年中的第几周(Week of year)
tags: date
expertise: advanced
author: chalarangelo
cover: blog_images/godray-computer-mug.jpg
firstSeen: 2021-08-15T05:00:00-04:00
---

### 返回日期对应的一年中的第几周(从零开始)。
> Returns the zero-indexed week of the year that a date corresponds to.

- 使用 `Date` 构造函数和 `Date.prototype.getFullYear()` 获取一年中的第一天作为 `Date` 对象。
- 使用 `Date.prototype.setDate()`、`Date.prototype.getDate()` 和 `Date.prototype.getDay()` 以及模 (`%`) 运算符来获取一年中的第一个星期一。
- 从给定的 `date` 中减去一年中的第一个星期一，然后除以一周中的毫秒数。
- 使用 `Math.round()` 获取与给定 `date` 相对应的一年中的零索引周。
- 如果给定的“日期”在一年中的第一个星期一之前，则返回 `-0`。

```js
const weekOfYear = date => {
  const startOfYear = new Date(date.getFullYear(), 0, 1);
  startOfYear.setDate(startOfYear.getDate() + (startOfYear.getDay() % 7));
  return Math.round((date - startOfYear) / (7 * 24 * 3600 * 1000));
};
```

```js
weekOfYear(new Date('2021-06-18')); // 23
```
