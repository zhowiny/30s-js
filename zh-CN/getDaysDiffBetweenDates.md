---
title: 计算以天为单位的日期差(Date difference in days)
tags: date
expertise: intermediate
cover: blog_images/spanish-resort.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2021-04-24T12:42:47+03:00
---

# 计算两个日期之间的差异（以天为单位）。
> Calculates the difference (in days) between two dates.

- 减去两个 `Date` 对象并除以一天中的毫秒数以获得它们之间的差异（以天为单位）。

```js
const getDaysDiffBetweenDates = (dateInitial, dateFinal) =>
  (dateFinal - dateInitial) / (1000 * 3600 * 24);
```

```js
getDaysDiffBetweenDates(new Date('2017-12-13'), new Date('2017-12-22')); // 9
```
