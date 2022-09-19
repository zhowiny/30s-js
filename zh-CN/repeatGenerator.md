---
title: 重复生成器(Repeat generator)
tags: function,generator
expertise: advanced
author: chalarangelo
cover: blog_images/white-flower.jpg
firstSeen: 2020-10-11T17:05:48+03:00
lastUpdated: 2020-10-11T17:05:48+03:00
---

### 创建一个生成器，无限期地重复给定的值。
> Creates a generator, repeating the given value indefinitely.

- 使用非终止的 `while` 循环，每次调用 `Generator.prototype.next()` 时都会产生一个值。
- 如果传递的值不是 `undefined`，则使用 `yield` 语句的返回值更新返回值。

```js
const repeatGenerator = function* (val) {
  let v = val;
  while (true) {
    let newV = yield v;
    if (newV !== undefined) v = newV;
  }
};
```

```js
const repeater = repeatGenerator(5);
repeater.next(); // { value: 5, done: false }
repeater.next(); // { value: 5, done: false }
repeater.next(4); // { value: 4, done: false }
repeater.next(); // { value: 4, done: false }
```
