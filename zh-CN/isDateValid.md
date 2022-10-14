---
title: 检查日期是否有效(Check if date is valid)
tags: date
expertise: intermediate
cover: blog_images/two-cities.jpg
firstSeen: 2020-10-08T16:39:23+03:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 检查是否可以从给定的值创建有效的日期对象。
> Checks if a valid date object can be created from the given values.

- 使用扩展运算符 (`...`) 将参数数组传递给 `Date` 构造函数。
- 使用 `Date.prototype.valueOf()` 和 `Number.isNaN()` 检查是否可以从给定值创建有效的 `Date` 对象。

```js
const isDateValid = (...val) => !Number.isNaN(new Date(...val).valueOf());
```

```js
isDateValid('December 17, 1995 03:24:00'); // true
isDateValid('1995-12-17T03:24:00'); // true
isDateValid('1995-12-17 T03:24:00'); // false
isDateValid('Duck'); // false
isDateValid(1995, 11, 17); // true
isDateValid(1995, 11, 17, 'Duck'); // false
isDateValid({}); // false
```
