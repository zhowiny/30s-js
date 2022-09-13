---
title: 特定底数的对数(Logarithm in specific base)
tags: math
expertise: beginner
cover: blog_images/yellow-white-mug-2.jpg
firstSeen: 2020-10-07T19:14:30+03:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 计算给定基数中给定数字的对数。
> Calculates the logarithm of the given number in the given base.

- 使用 `Math.log()` 从值和底中获取对数并将它们相除。

```js
const logBase = (n, base) => Math.log(n) / Math.log(base);
```

```js
logBase(10, 10); // 1
logBase(100, 10); // 2
```
