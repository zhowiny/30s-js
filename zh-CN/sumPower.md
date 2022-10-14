---
title: 范围内数字幂的总和(Sum of powers in range)
tags: math
expertise: intermediate
cover: blog_images/boat-port.jpg
firstSeen: 2018-01-01T15:49:25+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 计算从 `start` 到 `end`（包括两者）所有数字的幂的总和。
> Calculates the sum of the powers of all the numbers from `start` to `end` (both inclusive).

- 使用 `Array.prototype.fill()` 创建一个包含目标范围内所有数字的数组。
- 使用 `Array.prototype.map()` 和指数运算符 (`**`) 将它们提升到 `power` 和 `Array.prototype.reduce()` 以将它们相加。
- 省略第二个参数 `power`，使用默认的 `2` 幂。
- 省略第三个参数 `start`，以使用默认起始值 `1`。

```js
const sumPower = (end, power = 2, start = 1) =>
  Array(end + 1 - start)
    .fill(0)
    .map((x, i) => (i + start) ** power)
    .reduce((a, b) => a + b, 0);
```

```js
sumPower(10); // 385
sumPower(10, 3); // 3025
sumPower(10, 3, 5); // 2925
```
