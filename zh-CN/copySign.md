---
title: 将符号复制到数字(Copy sign to number)
tags: math
expertise: beginner
author: maciv
cover: blog_images/keyboard-tea.jpg
firstSeen: 2020-10-07T23:52:57+03:00
lastUpdated: 2020-10-07T23:52:57+03:00
---

### 返回第一个数字的绝对值，但返回第二个数字的符号。
> Returns the absolute value of the first number, but the sign of the second.

- 使用 `Math.sign()` 检查两个数字是否具有相同的符号。
- 如果有则返回 `x`，否则返回 `-x`（`0`，`-0`，`NaN` 这三种情况不适用）。

```js
const copySign = (x, y) => Math.sign(x) === Math.sign(y) ? x : -x;
```

```js
copySign(2, 3); // 2
copySign(2, -3); // -2
copySign(-2, 3); // 2
copySign(-2, -3); // -2
```

> [Math.sign](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/sign)
