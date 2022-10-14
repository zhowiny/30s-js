---
title: 数字是奇数(Number is odd)
tags: math
expertise: beginner
cover: blog_images/flower-portrait-5.jpg
firstSeen: 2019-09-25T20:35:06+03:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 检查给定的数字是否为奇数。
> Checks if the given number is odd.

- 使用模 (`%`) 运算符检查数字是奇数还是偶数。
- 如果数字是奇数，则返回 `true`，如果数字是偶数，则返回 `false`。

```js
const isOdd = num => num % 2 === 1;
```

```js
isOdd(3); // true
```
