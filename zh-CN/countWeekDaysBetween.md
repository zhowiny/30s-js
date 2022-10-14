---
title: 计算两个日期之间的工作日(Count weekdays between two dates)
tags: date
expertise: intermediate
cover: blog_images/organizer.jpg
firstSeen: 2020-10-11T11:44:44+03:00
lastUpdated: 2020-10-20T11:21:07+03:00
---

# 计算两个日期之间的工作日
> Counts the weekdays between two dates.

- 使用 `Array.from()` 构造一个 `length` 等于 `startDate` 和 `endDate` 之间的天数的数组。
- 使用 `Array.prototype.reduce()` 遍历数组，检查每个日期是否为工作日并递增 `count`。
- 使用 `Date.prototype.getDate()` 和 `Date.prototype.setDate()` 在每个循环的第二天更新 `startDate` 以将其提前一天。
- **注意：** 不考虑法定节假日。

```js
const countWeekDaysBetween = (startDate, endDate) =>
  Array
    .from({ length: (endDate - startDate) / (1000 * 3600 * 24) })
    .reduce(count => {
      if (startDate.getDay() % 6 !== 0) count++;
      startDate = new Date(startDate.setDate(startDate.getDate() + 1));
      return count;
    }, 0);
```

```js
countWeekDaysBetween(new Date('Oct 05, 2020'), new Date('Oct 06, 2020')); // 1
countWeekDaysBetween(new Date('Oct 05, 2020'), new Date('Oct 14, 2020')); // 7
```
