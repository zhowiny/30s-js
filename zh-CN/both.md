---
title: 函数逻辑与(Logical and for functions)
tags: function,logic
expertise: beginner
unlisted: true
cover: blog_images/succulent-2.jpg
firstSeen: 2020-05-13T11:35:36+03:00
lastUpdated: 2021-01-04T13:04:15+02:00
---

# 检查两个给定函数是否为给定的一组参数返回“true”。
> Checks if both of the given functions return `true` for a given set of arguments.

- 在使用提供的 `args` 调用两个函数的结果上使用逻辑和 (`&&`) 运算符。

```js
const both = (f, g) => (...args) => f(...args) && g(...args);
```

```js
const isEven = num => num % 2 === 0;
const isPositive = num => num > 0;
const isPositiveEven = both(isEven, isPositive);
isPositiveEven(4); // true
isPositiveEven(-2); // false
```
