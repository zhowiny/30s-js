---
title: 满足条件时应用函数(Apply function when condition is met)
tags: function,logic
expertise: beginner
cover: blog_images/flower-portrait-8.jpg
firstSeen: 2018-04-19T03:45:32+03:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

# 返回一个函数，该函数接受一个参数，如果为真则运行回调，如果为假则返回。
> Returns a function that takes one argument and runs a callback if it's truthy or returns it if falsy.

- 返回一个期望单个值的函数，`x`，它根据 `pred` 返回适当的值。

```js
const when = (pred, whenTrue) => x => (pred(x) ? whenTrue(x) : x);
```

```js
const doubleEvenNumbers = when(x => x % 2 === 0, x => x * 2);
doubleEvenNumbers(2); // 4
doubleEvenNumbers(1); // 1
```
