---
title: 一个月的最后一天(Last date of month)
tags: date
expertise: intermediate
cover: blog_images/polar-bear.jpg
firstSeen: 2020-10-09T20:36:54+03:00
lastUpdated: 2020-10-09T22:01:42+03:00
---

### 返回给定日期月份中最后一个日期的字符串表示形式。
> Returns the string representation of the last date in the given date's month.

- 使用 `Date.prototype.getFullYear()`、`Date.prototype.getMonth()` 从给定日期获取当前年份和月份。
- 使用 `Date` 构造函数创建一个新的日期，给定的年份和月份以 `1` 递增，日期设置为 `0`（上个月的最后一天）。
- 省略参数`date`，默认使用当前日期。

```js
const lastDateOfMonth = (date = new Date()) => {
  let d = new Date(date.getFullYear(), date.getMonth() + 1, 0);
  return d.toISOString().split('T')[0];
};
```

```js
lastDateOfMonth(new Date('2015-08-11')); // '2015-08-30'
```
