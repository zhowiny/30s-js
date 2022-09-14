---
title: 逻辑或非(Logical nor)
tags: math,logic
expertise: beginner
unlisted: true
cover: blog_images/succulent-8.jpg
firstSeen: 2021-03-29T21:20:41+03:00
lastUpdated: 2021-04-02T16:47:15+03:00
---

### 检查是否没有参数为 `true`。
> Checks if none of the arguments are `true`.

- 使用逻辑非 (`!`) 运算符返回两个给定值的逻辑或 (`||`) 的反数。

```js
const nor = (a, b) => !(a||b);
```

```js
nor(true, true); // false
nor(true, false); // false
nor(false, false); // true
```
