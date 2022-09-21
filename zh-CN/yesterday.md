---
title: 昨天的日期(Date of yesterday)
tags: date
expertise: intermediate
cover: blog_images/travel-mug-2.jpg
firstSeen: 2019-07-19T10:57:21+03:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

### 生成昨天日期的字符串表示形式。
> Results in a string representation of yesterday's date.

- 使用 `Date` 构造函数获取当前日期。
- 使用 `Date.prototype.getDate()` 将其减一，并使用 `Date.prototype.setDate()` 将值设置为结果。
- 使用 `Date.prototype.toISOString()` 以 `yyyy-mm-dd` 格式返回字符串。

```js
const yesterday = () => {
  let d = new Date();
  d.setDate(d.getDate() - 1);
  return d.toISOString().split('T')[0];
};
```

```js
yesterday(); // 2028-10-17 (如果当前日期是 2028-10-18)
```
