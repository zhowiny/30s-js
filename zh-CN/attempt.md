---
title: 尝试调用函数(Attempt invoking a function)
tags: function
expertise: intermediate
cover: blog_images/spanish-resort.jpg
firstSeen: 2018-01-28T14:44:40+02:00
lastUpdated: 2020-10-18T20:24:28+03:00
---

# 尝试使用提供的参数调用函数，返回结果或捕获的错误对象。
> Attempts to invoke a function with the provided arguments, returning either the result or the caught error object.

- 使用 `try...catch` 块返回函数的结果或适当的错误。
- 如果捕获的对象不是 `error`，则使用它来创建新的 `error`。

```js
const attempt = (fn, ...args) => {
  try {
    return fn(...args);
  } catch (e) {
    return e instanceof Error ? e : new Error(e);
  }
};
```

```js
var elements = attempt(function(selector) {
  return document.querySelectorAll(selector);
}, '>_>');
if (elements instanceof Error) elements = []; // elements = []
```
