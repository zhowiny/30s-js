---
title: 计算以分钟为单位的日期差(Date difference in minutes)
tags: date
expertise: beginner
author: maciv
cover: blog_images/flower-vase.jpg
firstSeen: 2021-04-24T12:48:49+03:00
lastUpdated: 2021-04-24T12:48:49+03:00
---

# 计算两个日期之间的差异（以分钟为单位）。
> Calculates the difference (in minutes) between two dates.

- 减去两个 `Date` 对象并除以一分钟的毫秒数以获得它们之间的差异（以分钟为单位）。

```js
const getMinutesDiffBetweenDates = (dateInitial, dateFinal) =>
  (dateFinal - dateInitial) / (1000 * 60);
```

```js
getMinutesDiffBetweenDates(
  new Date('2021-04-24 01:00:15'),
  new Date('2021-04-24 02:00:15')
); // 60
```
