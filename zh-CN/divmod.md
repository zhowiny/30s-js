---
title: 除法的商和模(Quotient and module of division)
tags: math
expertise: beginner
author: maciv
cover: blog_images/italian-horizon.jpg
firstSeen: 2020-10-07T23:59:13+03:00
lastUpdated: 2020-10-07T23:59:13+03:00
---

### 返回由给定数字的商和余数组成的数组。
> Returns an array consisting of the quotient and remainder of the given numbers.

- 使用 `Math.floor()` 得到除法 `x / y` 的商。
- 使用模运算符 (`%`) 获得除法 `x / y` 的余数。

```js
const divmod = (x, y) => [Math.floor(x / y), x % y];
```

```js
divmod(8, 3); // [2, 2]
divmod(3, 8); // [0, 3]
divmod(5, 5); // [1, 0]
```
