---
title: 逻辑或函数(Logical or for functions)
tags: function,logic
expertise: beginner
cover: blog_images/man-red-sunset.jpg
firstSeen: 2020-05-13T11:35:46+03:00
lastUpdated: 2020-10-19T18:51:03+03:00
---

### 检查是否至少有一个函数为给定的一组参数返回 `true`。
> Checks if at least one function returns `true` for a given set of arguments.

- 在使用提供的 `args` 调用两个函数的结果上使用逻辑或 (`||`) 运算符。

```js
const either = (f, g) => (...args) => f(...args) || g(...args);
```

```js
const isEven = num => num % 2 === 0;
const isPositive = num => num > 0;
const isPositiveOrEven = either(isPositive, isEven);
isPositiveOrEven(4); // true
isPositiveOrEven(3); // true
```
