---
title: 分割成行(Split into lines)
tags: string,regexp
expertise: beginner
cover: blog_images/two-cities.jpg
firstSeen: 2017-12-29T12:58:58+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 将多行字符串拆分为行数组。
> Splits a multiline string into an array of lines.

- 使用 `String.prototype.split()` 和正则表达式来匹配换行符并创建一个数组。

```js
const splitLines = str => str.split(/\r?\n/);
```

```js
splitLines('This\nis a\nmultiline\nstring.\n');
// ['This', 'is a', 'multiline', 'string.' , '']
```
