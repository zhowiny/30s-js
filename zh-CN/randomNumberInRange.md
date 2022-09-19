---
title: 范围内的随机数(Random number in range)
tags: math,random
expertise: beginner
cover: blog_images/white-laptop.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

### 生成指定范围内的随机数。
> Generates a random number in the specified range.

- 使用 `Math.random()` 生成随机值，使用乘法将其映射到所需范围。

```js
const randomNumberInRange = (min, max) => Math.random() * (max - min) + min;
```

```js
randomNumberInRange(2, 10); // 6.0211363285087005
```
