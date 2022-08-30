---
title: 柯里化函数(Curry function)
tags: function,recursion
expertise: advanced
cover: blog_images/rocky-beach-2.jpg
firstSeen: 2017-12-10T15:21:35+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 柯里化一个函数
> Curries a function.

- 使用递归。
- 如果提供的参数（`args`）的数量足够，则调用传递的函数`fn`。
- 否则，使用 `Function.prototype.bind()` 返回一个柯里化函数 `fn`，它需要其余的参数。
- 如果你想 curry 一个接受可变数量参数的函数（可变参数函数，例如`Math.min()`），你可以选择将参数数量传递给第二个参数`arity`。

```js
const curry = (fn, arity = fn.length, ...args) =>
  arity <= args.length ? fn(...args) : curry.bind(null, fn, arity, ...args);
```

```js
curry(Math.pow)(2)(10); // 1024
curry(Math.min, 3)(10)(50)(2); // 2
```
