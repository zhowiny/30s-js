---
title: 获取函数名(Get function name)
tags: function
expertise: beginner
cover: blog_images/flower-portrait-5.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 打印函数的名称。
> Logs the name of a function.

- 使用 `console.debug()` 和传递函数的 `name` 属性将函数的名称记录到控制台的 `debug` 通道。
- 返回给定的函数`fn`。

```js
const functionName = fn => (console.debug(fn.name), fn);
```

```js
let m = functionName(Math.max)(5, 6);
// max (打印在控制台Debug面板)
// m = 6
```
