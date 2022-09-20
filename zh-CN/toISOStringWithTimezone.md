---
title: 带时区的日期转 ISO 格式(Date to ISO format with timezone)
tags: date
expertise: intermediate
cover: blog_images/pop-of-green.jpg
firstSeen: 2020-10-07T09:25:05+03:00
lastUpdated: 2021-10-13T19:29:39+02:00
---

### 将日期转换为扩展 ISO 格式 (ISO 8601)，包括时区偏移。
> Converts a date to extended ISO format (ISO 8601), including timezone offset.

- 使用 `Date.prototype.getTimezoneOffset()` 获取时区偏移并将其反转。 将其符号存储在 `diff` 中。
- 定义一个辅助函数，`pad()`，使用 `Math.floor()` 和 `Math.abs()` 将任何传递的数字标准化为整数，并使用 `String.prototype` 将其填充为 `2` 位.padStart()`。
- 使用 `pad()` 和 `Date` 原型中的内置方法来构建具有时区偏移的 ISO 8601 字符串。

```js
const toISOStringWithTimezone = date => {
  const tzOffset = -date.getTimezoneOffset();
  const diff = tzOffset >= 0 ? '+' : '-';
  const pad = n => `${Math.floor(Math.abs(n))}`.padStart(2, '0');
  return date.getFullYear() +
    '-' + pad(date.getMonth() + 1) +
    '-' + pad(date.getDate()) +
    'T' + pad(date.getHours()) +
    ':' + pad(date.getMinutes()) +
    ':' + pad(date.getSeconds()) +
    diff + pad(tzOffset / 60) +
    ':' + pad(tzOffset % 60);
};
```

```js
toISOStringWithTimezone(new Date()); // '2020-10-06T20:43:33-04:00'
```
