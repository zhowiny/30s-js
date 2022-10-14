---
title: 数组总和(Array sum)
tags: math,array
expertise: beginner
cover: blog_images/lake-trees.jpg
firstSeen: 2017-12-29T13:29:49+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 计算两个或多个数字/数组的总和。
> Calculates the sum of two or more numbers/arrays.

- 使用 `Array.prototype.reduce()` 将每个值添加到累加器，初始值为 `0`。

```js
const sum = (...arr) => [...arr].reduce((acc, val) => acc + val, 0);
```

```js
sum(1, 2, 3, 4); // 10
sum(...[1, 2, 3, 4]); // 10
```
