---
title: 一个月的天数(Number of days in month)
tags: date
expertise: beginner
cover: blog_images/laptop-plants-2.jpg
firstSeen: 2021-06-13T05:00:00-04:00
---

### 获取指定 `年` 的给定 `月` 中的天数。
> Gets the number of days in the given `month` of the specified `year`.

- 使用 `Date` 构造函数从给定的 `year` 和 `month` 创建一个日期。
- 将 days 参数设置为 `0` 以获取上个月的最后一天，因为月份是零索引的。
- 使用 `Date.prototype.getDate()` 返回给定 `month` 中的天数。

```js
const daysInMonth = (year, month) => new Date(year, month, 0).getDate();
```

```js
daysInMonth(2020, 12); // 31
daysInMonth(2024, 2); // 29
```
