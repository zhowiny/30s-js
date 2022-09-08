---
title: Unix 时间戳转日期(Date from Unix timestamp)
tags: date
expertise: beginner
author: maciv
cover: blog_images/number-2.jpg
firstSeen: 2020-10-15T21:57:17+03:00
lastUpdated: 2020-10-15T21:57:17+03:00
---

### 从 Unix 时间戳创建一个 `Date` 对象。
> Creates a `Date` object from a Unix timestamp.

- 通过乘以“1000”将时间戳转换为毫秒。
- 使用 `Date` 构造函数创建一个新的 `Date` 对象。

```js
const fromTimestamp = timestamp => new Date(timestamp * 1000);
```

```js
fromTimestamp(1602162242); // 2020-10-08T13:04:02.000Z
```
