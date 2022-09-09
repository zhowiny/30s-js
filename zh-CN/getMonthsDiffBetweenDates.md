---
title: 计算以月为单位的日期差(Date difference in months)
tags: date
expertise: intermediate
author: maciv
cover: blog_images/two-flower-vases.jpg
firstSeen: 2020-08-07T15:15:26+03:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 计算两个日期之间的差异（以月为单位）。
> Calculates the difference (in months) between two dates.

- 使用 `Date.prototype.getFullYear()` 和 `Date.prototype.getMonth()` 计算两个 `Date` 对象之间的差异（以月为单位）。

```js
const getMonthsDiffBetweenDates = (dateInitial, dateFinal) =>
  Math.max(
    (dateFinal.getFullYear() - dateInitial.getFullYear()) * 12 +
      dateFinal.getMonth() -
      dateInitial.getMonth(),
    0
  );
```

```js
getMonthsDiffBetweenDates(new Date('2017-12-13'), new Date('2018-04-29')); // 4
```
