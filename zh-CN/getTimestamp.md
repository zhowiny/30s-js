---
title: 从日期获取 Unix 时间戳(Unix timestamp from date)
tags: date
expertise: beginner
cover: blog_images/interior-14.jpg
firstSeen: 2020-10-08T17:15:56+03:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 从 `Date` 对象获取 Unix 时间戳。
> Gets the Unix timestamp from a `Date` object.

- 使用 `Date.prototype.getTime()` 以毫秒为单位获取时间戳，然后除以 `1000` 以获取以秒为单位的时间戳。
- 使用 `Math.floor()` 将生成的时间戳适当地舍入为整数。
- 省略参数 `date` 以使用当前日期。

```js
const getTimestamp = (date = new Date()) => Math.floor(date.getTime() / 1000);
```

```js
getTimestamp(new Date('2020-10-19T22:49:51+03:00')); // 1603136991
```
