---
title: 检查是否是闰年(Check for leap year)
tags: date
expertise: beginner
cover: blog_images/flowering-hills.jpg
firstSeen: 2020-02-05T14:00:03+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 检查给定的 `year` 是否是闰年。
> Checks if the given `year` is a leap year.

- 使用 `Date` 构造函数，将日期设置为给定 `year` 的 2 月 29 日。
- 使用 `Date.prototype.getMonth()` 检查月份是否等于 `1`。

```js
const isLeapYear = year => new Date(year, 1, 29).getMonth() === 1;
```

```js
isLeapYear(2019); // false
isLeapYear(2020); // true
```
