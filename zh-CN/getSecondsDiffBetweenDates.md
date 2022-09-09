---
title: 计算以秒为单位的日期差(Date difference in seconds)
tags: date
expertise: beginner
cover: blog_images/laptop-journey.jpg
firstSeen: 2021-04-24T12:39:48+03:00
lastUpdated: 2021-04-24T12:39:48+03:00
---

### 计算两个日期之间的差异（以秒为单位）。
> Calculates the difference (in seconds) between two dates.

- 减去两个 `Date` 对象，然后除以毫秒数，得到它们之间的差异（以秒为单位）。

```js
const getSecondsDiffBetweenDates = (dateInitial, dateFinal) =>
  (dateFinal - dateInitial) / 1000;
```

```js
getSecondsDiffBetweenDates(
  new Date('2020-12-24 00:00:15'),
  new Date('2020-12-24 00:00:17')
); // 2
```
