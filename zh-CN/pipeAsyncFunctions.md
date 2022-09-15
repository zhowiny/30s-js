---
title: 管道异步函数(Pipe async functions)
tags: function,promise
expertise: intermediate
cover: blog_images/new-york-skyline.jpg
firstSeen: 2018-01-27T18:17:44+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

### 为异步函数执行从左到右的函数组合。
> Performs left-to-right function composition for asynchronous functions.

- 使用 `Array.prototype.reduce()` 和扩展运算符 (`...`) 使用 `Promise.prototype.then()` 执行函数组合。
- 函数可以返回正常值的组合，`Promise`s 或者是`async`，通过`await`返回。
- 所有函数都必须接受一个参数。

```js
const pipeAsyncFunctions = (...fns) =>
  arg => fns.reduce((p, f) => p.then(f), Promise.resolve(arg));
```

```js
const sum = pipeAsyncFunctions(
  x => x + 1,
  x => new Promise(resolve => setTimeout(() => resolve(x + 2), 1000)),
  x => x + 3,
  async x => (await x) + 4
);
(async() => {
  console.log(await sum(5)); // 15 (1秒后)
})();
```
