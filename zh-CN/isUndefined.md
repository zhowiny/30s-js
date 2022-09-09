---
title: 值是 undefined(Value is undefined)
tags: type
expertise: beginner
cover: blog_images/peaches.jpg
firstSeen: 2018-01-16T16:50:21+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 检查指定的值是否为 `undefined`。
> Checks if the specified value is `undefined`.

- 使用严格相等运算符检查 `val` 是否等于 `undefined`。

```js
const isUndefined = val => val === undefined;
```

```js
isUndefined(undefined); // true
```
