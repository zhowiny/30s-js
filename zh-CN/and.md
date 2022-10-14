---
title: 逻辑与(Logical and)
tags: math,logic
expertise: beginner
unlisted: true
cover: blog_images/succulent-1.jpg
firstSeen: 2020-05-13T11:35:31+03:00
lastUpdated: 2021-01-04T13:04:15+02:00
---

# 检查两个参数是否为`true`。
> Checks if both arguments are `true`.

- 对两个给定值使用逻辑与 (`&&`) 运算符。

```js
const and = (a, b) => a && b;
```

```js
and(true, true); // true
and(true, false); // false
and(false, false); // false
```
