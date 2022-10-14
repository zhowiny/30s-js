---
title: 前置函数参数(Prepend function arguments)
tags: function
expertise: intermediate
cover: blog_images/interior-6.jpg
firstSeen: 2018-01-24T14:40:16+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 创建一个调用 `fn` 的函数，并在其接收的参数前附加 `partials`。
> Creates a function that invokes `fn` with `partials` prepended to the arguments it receives.

- 使用扩展运算符 (`...`) 将 `partials` 添加到 `fn` 的参数列表中。

```js
const partial = (fn, ...partials) => (...args) => fn(...partials, ...args);
```

```js
const greet = (greeting, name) => greeting + ' ' + name + '!';
const greetHello = partial(greet, 'Hello');
greetHello('John'); // 'Hello John!'
```
