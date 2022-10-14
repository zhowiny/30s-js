---
title: 在指定的时间后resolve promise(Resolve promise after given amount of time)
tags: function,promise
expertise: intermediate
author: chalarangelo
cover: blog_images/filter-coffee-pot.jpg
firstSeen: 2022-01-08T05:00:00-04:00
---

# 创建一个promise，在给定的时间后resolve提供的值。
> Creates a promise that resolves after a given amount of time to the provided value.

- 使用 `Promise` 构造函数创建一个新的 Promise。
- 使用 `setTimeout()` 在指定的 `delay` 之后使用传递的 `value` 调用 promise 的 `resolve` 函数。

```js
const resolveAfter = (value, delay) =>
  new Promise(resolve => {
    setTimeout(() => resolve(value, delay));
  });
```

```js
resolveAfter('Hello', 1000);
// 返回一个promise，在 1 秒后resolve 'Hello'
```
