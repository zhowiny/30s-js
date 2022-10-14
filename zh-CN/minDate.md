---
title: 最小日期(Min date)
tags: date
expertise: intermediate
cover: blog_images/interior-2.jpg
firstSeen: 2018-09-29T13:38:20+03:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

# 返回给定日期的最小值。
> Returns the minimum of the given dates.

- 使用带有 `Math.min()` 的 ES6 扩展语法来查找最小日期值。
- 使用 `Date` 构造函数将其转换为 `Date` 对象。

```js
const minDate = (...dates) => new Date(Math.min(...dates));
```

```js
const dates = [
  new Date(2017, 4, 13),
  new Date(2018, 2, 12),
  new Date(2016, 0, 10),
  new Date(2016, 0, 9)
];
minDate(...dates); // 2016-01-08T22:00:00.000Z
```
