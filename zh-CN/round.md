---
title: 四舍五入到指定的精度(Round number to given precision)
tags: math
expertise: intermediate
cover: blog_images/yellow-white-mug-1.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 将数字四舍五入到指定的位数。
> Rounds a number to a specified amount of digits.

- 使用 `Math.round()` 和模板字符串将数字四舍五入到指定的位数。
- 省略第二个参数 `decimals`，以舍入为整数。

```js
const round = (n, decimals = 0) =>
  Number(`${Math.round(`${n}e${decimals}`)}e-${decimals}`);
```

```js
round(1.005, 2); // 1.01
(1.005).toFixed(2); // "1.00"
```
