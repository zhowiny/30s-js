---
title: 调用函数一次(Call function once)
tags: function
expertise: intermediate
cover: blog_images/pink-flower-tree.jpg
firstSeen: 2018-01-02T00:40:46+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 确保一个函数只被调用一次。
> Ensures a function is called only once.

- 利用闭包，使用标志，`call`，并在第一次调用函数时将其设置为 `true`，以防止再次调用它。
- 为了允许函数改变其 `this` 上下文（例如在事件监听器中），必须使用 `function` 关键字，并且提供的函数必须应用上下文。
- 允许使用 rest/spread (`...`) 运算符为函数提供任意数量的参数。

```js
const once = fn => {
  let called = false;
  return function(...args) {
    if (called) return;
    called = true;
    return fn.apply(this, args);
  };
};
```

```js
const startApp = function(event) {
  console.log(this, event); // document.body, MouseEvent
};
document.body.addEventListener('click', once(startApp));
// 点击后只运行一次`startApp`
```
