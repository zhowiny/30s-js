---
title: 转换函数参数(Transform function arguments)
tags: function
expertise: intermediate
cover: blog_images/flower-shape-sunset.jpg
firstSeen: 2018-01-28T14:54:16+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 创建一个函数，该函数调用提供的函数并转换其参数。
> Creates a function that invokes the provided function with its arguments transformed.

- 使用 `Array.prototype.map()` 将 `transforms` 应用于 `args` 并结合扩展运算符 (`...`) 将转换后的参数传递给 `fn`。

```js
const overArgs = (fn, transforms) =>
  (...args) => fn(...args.map((val, i) => transforms[i](val)));
```

```js
const square = n => n * n;
const double = n => n * 2;
const fn = overArgs((x, y) => [x, y], [square, double]);
fn(9, 3); // [81, 6]
```
