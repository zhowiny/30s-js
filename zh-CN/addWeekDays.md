---
title: 添加任意工作日到指定日期(Add weekdays to date)
tags: date
expertise: intermediate
cover: blog_images/digital-nomad-9.jpg
firstSeen: 2020-10-11T16:51:39+03:00
lastUpdated: 2021-01-08T00:23:44+02:00
---
# 添加给定的工作日数后计算日期。
> Calculates the date after adding the given number of business days.

- 使用 `Array.from()` 构造一个 `length` 等于要添加的工作日的 `count` 的数组。
- 使用 `Array.prototype.reduce()` 迭代数组，使用 `Date.prototype.getDate()` 和 `Date.prototype.setDate()`，从 `startDate` 开始并递增。
- 如果当前的“date”是周末，请添加一天或两天以使其成为工作日再次更新。
- **注意：** 不考虑法定节假日。

```js
const addWeekDays = (startDate, count) =>
  Array.from({ length: count }).reduce(date => {
    date = new Date(date.setDate(date.getDate() + 1));
    if (date.getDay() % 6 === 0)
      date = new Date(date.setDate(date.getDate() + (date.getDay() / 6 + 1)));
    return date;
  }, startDate);
```

```js
addWeekDays(new Date('Oct 09, 2020'), 5); // 'Oct 16, 2020'
addWeekDays(new Date('Oct 12, 2020'), 5); // 'Oct 19, 2020'
```
