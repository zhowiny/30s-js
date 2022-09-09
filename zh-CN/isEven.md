---
title: 数是偶数(Number is even)
tags: math
expertise: beginner
cover: blog_images/by-the-lighthouse.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 检查给定的数字是否是偶数。
> Checks if the given number is even.

- 使用模 (`%`) 运算符检查数字是奇数还是偶数。
- 如果数字是偶数，则返回 `true`，如果数字是奇数，则返回 `false`。

```js
const isEven = num => num % 2 === 0;
```

```js
isEven(3); // false
```
