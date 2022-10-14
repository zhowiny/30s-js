---
title: 从日期获取冒号时间(Get colon time from date)
tags: date,string
expertise: beginner
cover: blog_images/digital-nomad-5.jpg
firstSeen: 2018-01-13T17:14:48+02:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

# 从 `Date` 对象返回格式为 `HH:MM:SS` 的字符串。
> Returns a string of the form `HH:MM:SS` from a `Date` object.

- 使用 `Date.prototype.toTimeString()` 和 `String.prototype.slice()` 获取给定 `Date` 对象的 `HH:MM:SS` 部分。

```js
const getColonTimeFromDate = date => date.toTimeString().slice(0, 8);
```

```js
getColonTimeFromDate(new Date()); // '08:38:00'
```
