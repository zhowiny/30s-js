---
title: 逻辑异或(Logical xor)
tags: math,logic
expertise: beginner
unlisted: true
cover: blog_images/succulent-11.jpg
firstSeen: 2020-10-05T21:19:21+03:00
lastUpdated: 2021-01-04T13:04:15+02:00
---

### 检查是否只有一个参数为 `true`。
> Checks if only one of the arguments is `true`.

- 对两个给定值使用逻辑或 (`||`)、逻辑与(`&&`) 和非 (`!`) 运算符来创建逻辑异或。

```js
const xor = (a, b) => (( a || b ) && !( a && b ));
```

```js
xor(true, true); // false
xor(true, false); // true
xor(false, true); // true
xor(false, false); // false
```
