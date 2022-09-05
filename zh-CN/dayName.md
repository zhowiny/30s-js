---
title: 日期名称(Day name)
tags: date
expertise: beginner
cover: blog_images/interior.jpg
firstSeen: 2020-10-04T00:31:08+03:00
lastUpdated: 2020-11-01T20:50:57+02:00
---

### 从 `Date` 对象中获取工作日的名称。
> Gets the name of the weekday from a `Date` object.

- 使用 `Date.prototype.toLocaleDateString()` 和 `{ weekday: 'long' }` 选项来检索工作日。
- 使用可选的第二个参数来获取特定于语言的名称或省略它以使用默认语言环境。

```js
const dayName = (date, locale) =>
  date.toLocaleDateString(locale, { weekday: 'long' });
```

```js
dayName(new Date()); // 'Saturday'
dayName(new Date('09/23/2020'), 'de-DE'); // 'Samstag'
dayName(new Date('2022-09-05'), 'zh-CN'); // '星期一'
```
