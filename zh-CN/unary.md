---
title: 一元函数(Unary function arity)
tags: function
expertise: beginner
cover: blog_images/flower-portrait-2.jpg
firstSeen: 2018-01-24T13:22:32+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

### 创建一个最多接受一个参数的函数，忽略任何其他参数。
> Creates a function that accepts up to one argument, ignoring any additional arguments.

- 调用提供的函数，`fn`，只提供第一个参数。

```js
const unary = fn => val => fn(val);
```

```js
['6', '8', '10'].map(unary(parseInt)); // [6, 8, 10]
```
