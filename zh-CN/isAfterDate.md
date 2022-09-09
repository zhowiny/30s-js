---
title: 检查日期是否在另一个日期之后(Check if date is after another date)
tags: date
expertise: beginner
cover: blog_images/flower-portrait-4.jpg
firstSeen: 2018-09-29T13:58:38+03:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 检查一个日期是否在另一个日期之后。
> Checks if a date is after another date.

- 使用大于运算符 (`>`) 检查第一个日期是否在第二个日期之后。

```js
const isAfterDate = (dateA, dateB) => dateA > dateB;
```

```js
isAfterDate(new Date(2010, 10, 21), new Date(2010, 10, 20)); // true
```
