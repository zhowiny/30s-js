---
title: 将函数`promise`化(Promisify function)
tags: function,promise
expertise: intermediate
cover: blog_images/duck-plants.jpg
firstSeen: 2017-12-13T12:27:43+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

### 将一个不是promise的函数转换成 promise 。
> Converts an asynchronous function to return a promise.

- 使用柯里化返回一个函数，该函数返回一个调用原始函数的 `Promise`。
- 使用剩余运算符 (`...`) 传递所有参数。
- **注意：** 在 Node 8+ 中，您可以使用 [`util.promisify`](https://nodejs.org/api/util.html#util_util_promisify_original)。

```js
const promisify = func => (...args) =>
  new Promise((resolve, reject) =>
    func(...args, (err, result) => (err ? reject(err) : resolve(result)))
  );
```

```js
const delay = promisify((d, cb) => setTimeout(cb, d));
delay(2000).then(() => console.log('Hi!')); // Promise resolves after 2s
```
