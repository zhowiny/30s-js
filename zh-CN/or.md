---
title: 逻辑或(Logical or)
tags: math,logic
expertise: beginner
unlisted: true
cover: blog_images/succulent-4.jpg
firstSeen: 2020-05-13T11:35:41+03:00
lastUpdated: 2021-01-04T13:04:15+02:00
---

### 检查是否至少有一个参数为 `true`。
> Checks if at least one of the arguments is `true`.

- 对两个给定值使用逻辑或 (`||`) 运算符。

```js
const or = (a, b) => a || b;
```

```js
or(true, true); // true
or(true, false); // true
or(false, false); // false
```
