---
title: 在参数上调用函数(Invoke functions on arguments)
tags: function
expertise: intermediate
cover: blog_images/jars-on-shelf.jpg
firstSeen: 2018-01-23T21:02:17+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 创建一个函数，该函数使用它接收的参数调用每个提供的函数并返回结果。
> Creates a function that invokes each provided function with the arguments it receives and returns the results.

- 使用 `Array.prototype.map()` 和 `Function.prototype.apply()` 将每个函数应用于给定的参数。

```js
const over = (...fns) => (...args) => fns.map(fn => fn.apply(null, args));
```

```js
const minMax = over(Math.min, Math.max);
minMax(1, 2, 3, 4, 5); // [1, 5]
```
