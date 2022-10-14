---
title: 一年中的一天(Day of year)
tags: date
expertise: beginner
cover: blog_images/interior-3.jpg
firstSeen: 2018-09-29T13:22:20+03:00
lastUpdated: 2020-10-19T18:51:03+03:00
---

# 从 `Date` 对象获取一年中的某一天（数字范围为 1-366）。
> Gets the day of the year (number in the range 1-366) from a `Date` object.

- 使用 `Date` 构造函数和 `Date.prototype.getFullYear()` 获取一年中的第一天作为 `Date` 对象。
- 从 `date` 中减去一年中的第一天，然后除以每天的毫秒数以获得结果。
- 使用 `Math.floor()` 将结果天数适当地四舍五入为整数。

```js
const dayOfYear = date =>
  Math.floor((date - new Date(date.getFullYear(), 0, 0)) / 1000 / 60 / 60 / 24);
```

```js
dayOfYear(new Date('2022-09-29')); // 272
```
