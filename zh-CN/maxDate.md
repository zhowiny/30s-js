---
title: 最大日期(Max date)
tags: date
expertise: intermediate
cover: blog_images/interior-15.jpg
firstSeen: 2018-09-29T13:38:20+03:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

# 返回给定日期的最大值。
> Returns the maximum of the given dates.

- 使用带有 `Math.max()` 的 ES6 扩展语法来查找最大日期值。
- 使用 `Date` 构造函数将其转换为 `Date` 对象。

```js
const maxDate = (...dates) => new Date(Math.max(...dates));
```

```js
const dates = [
  new Date(2017, 4, 13),
  new Date(2018, 2, 12),
  new Date(2016, 0, 10),
  new Date(2016, 0, 9)
];
maxDate(...dates); // 2018-03-11T22:00:00.000Z
```
