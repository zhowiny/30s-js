---
title: 检查日期是否早于另一个日期(Check if date is before another date)
tags: date
expertise: beginner
cover: blog_images/flower-portrait-3.jpg
firstSeen: 2018-09-29T13:58:38+03:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 检查一个日期是否早于另一个日期。
> Checks if a date is before another date.

- 使用小于运算符 (`<`) 检查第一个日期是否在第二个日期之前。

```js
const isBeforeDate = (dateA, dateB) => dateA < dateB;
```

```js
isBeforeDate(new Date(2010, 10, 20), new Date(2010, 10, 21)); // true
```
