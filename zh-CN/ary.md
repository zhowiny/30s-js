---
title: 指定函数参数数量(Function arity)
tags: function
expertise: advanced
cover: blog_images/trippy-chemicals.jpg
firstSeen: 2018-01-24T13:59:54+02:00
lastUpdated: 2020-10-18T20:24:28+03:00
---

### 创建一个最多接受“n”个参数的函数，忽略任何其他参数。
> Creates a function that accepts up to `n` arguments, ignoring any additional arguments.

- 使用 `Array.prototype.slice()` 和扩展运算符 (`...`) 调用提供的函数 `fn`，最多有 `n` 个参数。

```js
const ary = (fn, n) => (...args) => fn(...args.slice(0, n));
```

```js
const firstTwoMax = ary(Math.max, 2);
[[2, 6, 'a'], [6, 4, 8], [10]].map(x => firstTwoMax(...x)); // [6, 6, 10]
```
