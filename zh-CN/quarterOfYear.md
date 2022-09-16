---
title: 一年的季度(Quarter of year)
tags: date
expertise: beginner
cover: blog_images/fallen-leaves.jpg
firstSeen: 2020-10-09T10:23:55+03:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

### 返回提供的日期所属的季度和年份。
> Returns the quarter and year to which the supplied date belongs to.

- 使用 `Date.prototype.getMonth()` 获取范围 (0, 11) 中的当前月份，添加 `1` 将其映射到范围 (1, 12)。
- 使用 `Math.ceil()` 并将月份除以 `3` 以获得当前季度。
- 使用 `Date.prototype.getFullYear()` 从给定的 `date` 中获取年份。
- 省略参数`date`，默认使用当前日期。

```js
const quarterOfYear = (date = new Date()) => [
  Math.ceil((date.getMonth() + 1) / 3),
  date.getFullYear()
];
```

```js
quarterOfYear(new Date('07/10/2018')); // [ 3, 2018 ]
quarterOfYear(); // [ 4, 2020 ]
```
