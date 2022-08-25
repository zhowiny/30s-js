---
title: 添加任意分钟到指定日期(Add minutes to date)
tags: date
expertise: intermediate
cover: blog_images/lake-trees.jpg
firstSeen: 2020-11-28T19:27:46+02:00
lastUpdated: 2020-11-28T19:27:46+02:00
---

### 计算从给定日期算起的“n”分钟的日期，返回其字符串表示形式。
> Calculates the date of `n` minutes from the given date, returning its string representation.

- 从第一个参数使用 `Date` 构造函数, 创建 `Date` 对象.
- 使用 `Date.prototype.getTime()` 和 `Date.prototype.setTime()` to add `n`  添加 `n` 分钟 至给定的日期.
- 使用 `Date.prototype.toISOString()`, `String.prototype.split()` 和 `String.prototype.replace()` 返回 `yyyy-mm-dd HH:MM:SS` 格式字符串.


```js
const addMinutesToDate = (date, n) => {
  const d = new Date(date);
  d.setTime(d.getTime() + n * 60000);
  return d.toISOString().split('.')[0].replace('T',' ');
};
```

```js
addMinutesToDate('2020-10-19 12:00:00', 10); // '2020-10-19 12:10:00'
addMinutesToDate('2020-10-19', -10); // '2020-10-18 23:50:00'
```
