---
title: 检查日期是否在两个日期之间(Check if date is between two dates)
tags: date
expertise: beginner
cover: blog_images/flower-portrait-6.jpg
firstSeen: 2020-10-07T20:31:52+03:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 检查日期是否在其他两个日期之间。
> Checks if a date is between two other dates.

- 使用大于 (`>`) 和小于 (`<`) 运算符来检查 `date` 是否介于 `dateStart` 和 `dateEnd` 之间。

```js
const isBetweenDates = (dateStart, dateEnd, date) =>
  date > dateStart && date < dateEnd;
```

```js
isBetweenDates(
  new Date(2010, 11, 20),
  new Date(2010, 11, 30),
  new Date(2010, 11, 19)
); // false
isBetweenDates(
  new Date(2010, 11, 20),
  new Date(2010, 11, 30),
  new Date(2010, 11, 25)
); // true
```
