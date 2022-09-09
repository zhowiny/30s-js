---
title: 值为不存在(Value is nil)
tags: type
expertise: beginner
cover: blog_images/river-houses.jpg
firstSeen: 2018-01-16T16:50:21+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 检查指定的值是 `null` 或者 `undefined`。
> Checks if the specified value is `null` or `undefined`.

- 使用严格相等运算符检查 `val` 的值是否等于 `null` 或 `undefined`。

```js
const isNil = val => val === undefined || val === null;
```

```js
isNil(null); // true
isNil(undefined); // true
isNil(''); // false
```
