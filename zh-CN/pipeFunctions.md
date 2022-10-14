---
title: 管道函数(Pipe functions)
tags: function
expertise: intermediate
cover: blog_images/goat-wooden-cottage.jpg
firstSeen: 2017-12-26T19:02:27+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 执行从左到右的功能组合。
> Performs left-to-right function composition.

- 使用 `Array.prototype.reduce()` 和扩展运算符（`...`）来执行从左到右的函数组合。
- 第一个（最左边的）函数可以接受一个或多个参数； 其余函数必须是一元的。

```js
const pipeFunctions = (...fns) =>
  fns.reduce((f, g) => (...args) => g(f(...args)));
```

```js
const add5 = x => x + 5;
const multiply = (x, y) => x * y;
const multiplyAndAdd5 = pipeFunctions(multiply, add5);
multiplyAndAdd5(5, 2); // 15
```
