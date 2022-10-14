---
title: 组合函数(Compose functions)
tags: function
expertise: intermediate
cover: blog_images/digital-nomad-16.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 执行从右到左的函数组合。
> Performs right-to-left function composition.

- 使用 `Array.prototype.reduce()` 执行从右到左的函数组合。
- 最后一个（最右边的）函数可以接受一个或多个参数； 其余函数必须是一元的。

```js
const compose = (...fns) =>
  fns.reduce((f, g) => (...args) => f(g(...args)));
```

```js
const add5 = x => x + 5;
const multiply = (x, y) => x * y;
const multiplyAndAdd5 = compose(
  add5,
  multiply
);
multiplyAndAdd5(5, 2); // 15
```
