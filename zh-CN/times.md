---
title: 迭代 n 次(Iterate n times)
tags: function
expertise: intermediate
cover: blog_images/lake-loop.jpg
firstSeen: 2018-01-24T13:50:49+02:00
lastUpdated: 2020-10-20T11:21:07+03:00
---

# 迭代回调`n`次。
> Iterates over a callback `n` times.

- 使用 `Function.prototype.call()` 调用 `fn` `n` 次或直到它返回 `false`。
- 省略最后一个参数 `context` 以使用 `undefined` 对象（或非严格模式下的全局对象）。

```js
const times = (n, fn, context = undefined) => {
  let i = 0;
  while (fn.call(context, i) !== false && ++i < n) {}
};
```

```js
var output = '';
times(5, i => (output += i));
console.log(output); // 01234
```
