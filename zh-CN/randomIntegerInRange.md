---
title: 范围内的随机整数(Random integer in range)
tags: math,random
expertise: beginner
cover: blog_images/painters-desk.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

### 生成指定范围内的随机整数。
> Generates a random integer in the specified range.

- 使用 `Math.random()` 生成随机数并将其映射到所需范围。
- 使用 `Math.floor()` 使其成为整数。

```js
const randomIntegerInRange = (min, max) =>
  Math.floor(Math.random() * (max - min + 1)) + min;
```

```js
randomIntegerInRange(0, 5); // 2
```
