---
title: 计算以小时为单位的日期差(Date difference in hours)
tags: date
expertise: beginner
author: maciv
cover: blog_images/tram-car-2.jpg
firstSeen: 2021-04-24T12:56:21+03:00
lastUpdated: 2021-04-24T12:56:21+03:00
---

# 计算两个日期之间的差异（以小时为单位）。
> Calculates the difference (in hours) between two dates.

- 减去两个 `Date` 对象并除以一小时内的毫秒数以获得它们之间的差异（以小时为单位）。

```js
const getHoursDiffBetweenDates = (dateInitial, dateFinal) =>
  (dateFinal - dateInitial) / (1000 * 3600);
```

```js
getHoursDiffBetweenDates(
  new Date('2021-04-24 10:25:00'),
  new Date('2021-04-25 10:25:00')
); // 24
```
