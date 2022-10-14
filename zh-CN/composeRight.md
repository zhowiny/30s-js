---
title: 反向组合函数(Reverse compose functions)
tags: function
expertise: intermediate
cover: blog_images/rocky-beach.jpg
firstSeen: 2018-01-23T22:12:56+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 执行从左到右的功能组合。
> Performs left-to-right function composition.

- 使用 `Array.prototype.reduce()` 执行从左到右的函数组合。
- 第一个（最左边的）函数可以接受一个或多个参数； 其余函数必须是一元的。

```js
const composeRight = (...fns) =>
  fns.reduce((f, g) => (...args) => g(f(...args)));
```

```js
const add = (x, y) => x + y;
const square = x => x * x;
const addAndSquare = composeRight(add, square);
addAndSquare(1, 2); // 9
```
