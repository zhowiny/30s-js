---
title: 延迟函数执行(Delay function execution)
tags: function
expertise: intermediate
cover: blog_images/interior-13.jpg
firstSeen: 2018-01-24T14:32:20+02:00
lastUpdated: 2020-10-19T18:51:03+03:00
---

### 在 `ms` 毫秒后调用提供的函数。
> Invokes the provided function after `ms` milliseconds.

- 使用 `setTimeout()` 来延迟 `fn` 的执行。
- 使用展开 (`...`) 运算符为函数提供任意数量的参数。

```js
const delay = (fn, ms, ...args) => setTimeout(fn, ms, ...args);
```

```js
delay(
  function(text) {
    console.log(text);
  },
  1000,
  'later'
); // 1秒后打印 'later'.
```
