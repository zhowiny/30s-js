---
title: 从现在开始 `n` 天前的日期(Days ago)
tags: date
expertise: beginner
cover: blog_images/sunrise-over-city.jpg
firstSeen: 2020-10-06T05:35:23+03:00
lastUpdated: 2022-01-30T11:48:07+03:00
---

### 以字符串表示形式计算从今天开始的 `n` 天前的日期。
> Calculates the date of `n` days ago from today as a string representation.

- 使用 `Date` 构造函数获取当前日期。
- 使用 `Math.abs()` 和 `Date.prototype.getDate()` 相应地更新日期并使用 `Date.prototype.setDate()` 设置结果。
- 使用 `Date.prototype.toISOString()` 以 `yyyy-mm-dd` 格式返回字符串。

```js
const daysAgo = n => {
  let d = new Date();
  d.setDate(d.getDate() - Math.abs(n));
  return d.toISOString().split('T')[0];
};
```

```js
daysAgo(20); // 2020-09-16 (如果当前日期是 2020-10-06)
```
