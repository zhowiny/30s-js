---
title: 反转数字(Reverse number)
tags: math,string
expertise: beginner
cover: blog_images/walking.jpg
firstSeen: 2020-07-17T16:41:28+03:00
lastUpdated: 2020-09-18T21:19:23+03:00
---

# 反转一个数字。
> Reverses a number.

- 使用 `Object.prototype.toString()` 将 `n` 转换为字符串。
- 使用 `String.prototype.split()`、`Array.prototype.reverse()` 和 `Array.prototype.join()` 将 `n` 的反转值作为字符串。
- 使用 `parseFloat()` 将字符串转换为数字，并使用 `Math.sign()` 保留其符号。

```js
const reverseNumber = n =>
  parseFloat(`${n}`.split('').reverse().join('')) * Math.sign(n);
```

```js
reverseNumber(981); // 189
reverseNumber(-500); // -5
reverseNumber(73.6); // 6.37
reverseNumber(-5.23); // -32.5
```
