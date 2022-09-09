---
title: 日期是周末(Date is weekend)
tags: date
expertise: beginner
cover: blog_images/tropical-bike.jpg
firstSeen: 2019-07-19T17:07:02+03:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 检查给定日期是否是周末。
> Checks if the given date is a weekend.

- 使用 `Date.prototype.getDay()` 通过模运算符 (`%`) 检查周末。
- 省略参数 `d`，以使用当前日期作为默认值。

```js
const isWeekend = (d = new Date()) => d.getDay() % 6 === 0;
```

```js
isWeekend(); // 2018-10-19 (if current date is 2018-10-18)
```
