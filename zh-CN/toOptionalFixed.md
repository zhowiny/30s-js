---
title: 定点表示法格式化数值，不带尾数零(Number to fixed-point notation without trailing zeros)
tags: math,string
expertise: beginner
author: chalarangelo
cover: blog_images/red-succulent.jpg
firstSeen: 2022-05-10T05:00:00-04:00
---

### 如果数字有小数，则使用定点表示法格式化数字。
> Formats a number using fixed-point notation, if it has decimals.

- 使用 `Number.prototype.toFixed()` 将数字转换为定点符号字符串。
- 使用 `Number.parseFloat()` 将定点符号字符串转换为数字，删除尾随零。
- 使用模板文字将数字转换为字符串。

```js
const toOptionalFixed = (num, digits) =>
  `${Number.parseFloat(num.toFixed(digits))}`;
```

```js
toOptionalFixed(1, 2); // '1'
toOptionalFixed(1.001, 2); // '1'
toOptionalFixed(1.500, 2); // '1.5'
```
