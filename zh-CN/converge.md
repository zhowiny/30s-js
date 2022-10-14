---
title: 收敛分支函数(Converge branching functions)
tags: function
expertise: intermediate
excerpt: 将分支函数列表聚合为单个函数并返回结果。
cover: blog_images/cherry-trees.jpg
firstSeen: 2018-02-07T12:23:04+02:00
lastUpdated: 2021-01-08T00:23:44+02:00
---

# 接受一个收敛函数和一个分支函数列表，并返回一个函数，该函数将每个分支函数应用于参数，分支函数的结果作为参数传递给收敛函数。
> Accepts a converging function and a list of branching functions and returns a function that applies each branching function to the arguments and the results of the branching functions are passed as arguments to the converging function.

- 使用 `Array.prototype.map()` 和 `Function.prototype.apply()` 将每个函数应用于给定的参数。
- 使用扩展运算符 (`...`) 调用 `converger` 以及所有其他函数的结果。

```js
const converge = (converger, fns) => (...args) =>
  converger(...fns.map(fn => fn.apply(null, args)));
```

```js
const average = converge((a, b) => a / b, [
  arr => arr.reduce((a, v) => a + v, 0),
  arr => arr.length
]);
average([1, 2, 3, 4, 5, 6, 7]); // 4
```
