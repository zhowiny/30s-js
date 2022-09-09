---
title: 值为 null(Value is null)
tags: type
expertise: beginner
cover: blog_images/broken-screen.jpg
firstSeen: 2017-12-31T12:26:19+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 检查指定的值是否为 `null`。
> Checks if the specified value is `null`.

- 使用严格相等运算符检查 `val` 的值是否等于 `null`。

```js
const isNull = val => val === null;
```

```js
isNull(null); // true
```
