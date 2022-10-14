---
title: 调用或者返回(Call or return)
tags: function
expertise: beginner
author: chalarangelo
cover: blog_images/cows.jpg
firstSeen: 2022-04-04T05:00:00-04:00
---

# 如果它是一个函数，则调用该参数，否则返回它。
> Calls the argument if it's a function, otherwise returns it.

- 使用 `typeof` 运算符检查给定参数是否为函数。
- 如果是，请使用扩展运算符 (`...`) 将其与给定参数的其余部分一起调用。 否则返回它。

```js
const callOrReturn = (fn, ...args) =>
  typeof fn === 'function' ? fn(...args) : fn;
```

```js
callOrReturn(x => x + 1, 1); // 2
callOrReturn(1, 1); // 1
```
