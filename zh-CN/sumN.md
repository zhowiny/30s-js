---
title: 从 1 到 n 的数字总和(Sum of numbers until n)
tags: math
expertise: beginner
cover: blog_images/blue-flower.jpg
firstSeen: 2020-10-08T16:52:55+03:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 对 `1` 和 `n` 之间的所有数字求和。
> Sums all the numbers between `1` and `n`.

- 使用公式 `(n * (n + 1)) / 2` 得到 1 和 `n` 之间所有数字的总和。

```js
const sumN = n => (n * (n + 1)) / 2;
```

```js
sumN(100); // 5050
```
