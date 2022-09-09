---
title: 日期与另一个日期相同(Date is same as another date)
tags: date
expertise: beginner
cover: blog_images/pineapple-at-work.jpg
firstSeen: 2018-09-29T13:58:38+03:00
lastUpdated: 2020-11-03T22:11:18+02:00
---

### 检查一个日期是否与另一个日期相同。
> Checks if a date is the same as another date.

- 使用 `Date.prototype.toISOString()` 和严格相等检查 (`===`) 来检查第一个日期是否与第二个日期相同。

```js
const isSameDate = (dateA, dateB) =>
  dateA.toISOString() === dateB.toISOString();
```

```js
isSameDate(new Date(2010, 10, 20), new Date(2010, 10, 20)); // true
```
