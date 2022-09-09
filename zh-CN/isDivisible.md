---
title: 数是可整除的(Number is divisible)
tags: math
expertise: beginner
cover: blog_images/clutter-2.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

### 检查第一个数字参数是否可以被第二个整除。
> Checks if the first numeric argument is divisible by the second one.

- 使用模运算符 (`%`) 检查余数是否等于 `0`。

```js
const isDivisible = (dividend, divisor) => dividend % divisor === 0;
```

```js
isDivisible(6, 3); // true
```
