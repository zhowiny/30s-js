---
title: 获取整数的12小时制后缀(Get meridiem suffix of integer)
tags: date
expertise: beginner
cover: blog_images/dark-leaves-4.jpg
firstSeen: 2018-01-13T17:14:48+02:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 将整数转换为后缀字符串，根据其值添加 `am` 或 `pm`。
> Converts an integer to a suffixed string, adding `am` or `pm` based on its value.

- 使用模运算符 (`%`) 和条件检查将整数转换为带有 `meridiem` 后缀的字符串化 12 小时格式。

```js
const getMeridiemSuffixOfInteger = num =>
  num === 0 || num === 24
    ? 12 + 'am'
    : num === 12
    ? 12 + 'pm'
    : num < 12
    ? (num % 12) + 'am'
    : (num % 12) + 'pm';
```

```js
getMeridiemSuffixOfInteger(0); // '12am'
getMeridiemSuffixOfInteger(11); // '11am'
getMeridiemSuffixOfInteger(13); // '1pm'
getMeridiemSuffixOfInteger(25); // '1pm'
```
