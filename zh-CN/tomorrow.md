---
title: 明天的日期(Date of tomorrow)
tags: date
expertise: intermediate
cover: blog_images/travel-mug-2.jpg
firstSeen: 2017-12-26T18:56:24+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 结果是明天日期的字符串表示形式。
> Results in a string representation of tomorrow's date.

- 使用 `Date` 构造函数获取当前日期。
- 使用 `Date.prototype.getDate()` 将其加一，并使用 `Date.prototype.setDate()` 将值设置为结果。
- 使用 `Date.prototype.toISOString()` 以 `yyyy-mm-dd` 格式返回字符串。

```js
const tomorrow = () => {
  let d = new Date();
  d.setDate(d.getDate() + 1);
  return d.toISOString().split('T')[0];
};
```

```js
tomorrow(); // 2018-10-19 (if current date is 2018-10-18)
```
