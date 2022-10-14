---
title: 添加任意天数到指定日期(Add days to date)
tags: date
expertise: intermediate
cover: blog_images/digital-nomad-12.jpg
firstSeen: 2020-10-12T03:03:18+03:00
lastUpdated: 2020-11-28T19:18:29+02:00
---

# 从给定日期计算“n”天的日期，返回其字符串表示形式。
> Calculates the date of `n` days from the given date, returning its string representation.

- 从第一个参数使用 `Date` 构造函数, 创建 `Date` 对象.
- 使用 `Date.prototype.getDate()` 和 `Date.prototype.setDate()` 添加 `n` 天 至给定的日期.
- 使用 `Date.prototype.toISOString()` 返回 `yyyy-mm-dd` 格式的字符串.

```js
const addDaysToDate = (date, n) => {
  const d = new Date(date);
  d.setDate(d.getDate() + n);
  return d.toISOString().split('T')[0];
};
```

```js
addDaysToDate('2020-10-15', 10); // '2020-10-25'
addDaysToDate('2020-10-15', -10); // '2020-10-05'
```
