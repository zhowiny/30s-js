---
title: 数值的乘积(Product of numeric values)
tags: math,array
expertise: intermediate
author: maciv
cover: blog_images/travel-mug-1.jpg
firstSeen: 2020-10-15T21:56:51+03:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

### 计算两个或多个数字/数组的乘积。
> Calculates the product of two or more numbers/arrays.

- 使用 `Array.prototype.reduce()` 将每个值与累加器相乘，初始值为 `1`。

```js
const prod = (...arr) => [...arr].reduce((acc, val) => acc * val, 1);
```

```js
prod(1, 2, 3, 4); // 24
prod(...[1, 2, 3, 4]); // 24
```
