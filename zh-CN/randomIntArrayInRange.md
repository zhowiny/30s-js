---
title: 范围内的随机整数数组(Random integer array in range)
tags: math,random
expertise: intermediate
cover: blog_images/digital-nomad-11.jpg
firstSeen: 2018-01-15T13:25:18+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

### 生成指定范围内的 `n` 个随机整数数组。
> Generates an array of `n` random integers in the specified range.

- 使用 `Array.from()` 创建一个特定长度的空数组。
- 使用 `Math.random()` 生成随机数并将它们映射到所需的范围，使用 `Math.floor()` 使它们成为整数。

```js
const randomIntArrayInRange = (min, max, n = 1) =>
  Array.from(
    { length: n },
    () => Math.floor(Math.random() * (max - min + 1)) + min
  );
```

```js
randomIntArrayInRange(12, 35, 10); // [ 34, 14, 27, 17, 30, 27, 20, 26, 21, 14 ]
```
