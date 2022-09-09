---
title: 日期是工作日(Date is weekday)
tags: date
expertise: beginner
cover: blog_images/typewriter.jpg
firstSeen: 2019-07-19T12:12:09+03:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 检查给定日期是否为工作日。
> Checks if the given date is a weekday.

- 使用 `Date.prototype.getDay()` 通过取模运算符 (`%`) 检查工作日。
- 省略参数 `d`，以使用当前日期作为默认值。

```js
const isWeekday = (d = new Date()) => d.getDay() % 6 !== 0;
```

```js
isWeekday(); // true (if current date is 2019-07-19)
```
