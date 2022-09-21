---
title: 非柯里化函数(Uncurry function)
tags: function
expertise: advanced
cover: blog_images/perfect-timing.jpg
firstSeen: 2018-02-14T11:56:44+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

### 去柯里化一个函数直到深度 `n`。
> Uncurries a function up to depth `n`.

- 返回一个可变参数函数。
- 在提供的参数上使用 `Array.prototype.reduce()` 来调用函数的每个后续 curry 级别。
- 如果提供的参数的 `length` 小于 `n` ，则抛出错误。
- 否则，使用 `Array.prototype.slice()` 使用适当数量的参数调用 `fn`。
- 省略第二个参数，`n`，以 uncurry 到深度 `1`。

```js
const uncurry = (fn, n = 1) => (...args) => {
  const next = acc => args => args.reduce((x, y) => x(y), acc);
  if (n > args.length) throw new RangeError('Arguments too few!');
  return next(fn)(args.slice(0, n));
};
```

```js
const add = x => y => z => x + y + z;
const uncurriedAdd = uncurry(add, 3);
uncurriedAdd(1, 2, 3); // 6
```
