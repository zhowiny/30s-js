---
title: 附加函数参数(Append function arguments)
tags: function
expertise: intermediate
cover: blog_images/jars-on-shelf-2.jpg
firstSeen: 2018-01-24T14:40:16+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 创建一个调用 `fn` 的函数，并将 `partials` 附加到它接收的参数中。
> Creates a function that invokes `fn` with `partials` appended to the arguments it receives.

- 使用扩展运算符 (`...`) 将 `partials` 附加到 `fn` 的参数列表中。

```js
const partialRight = (fn, ...partials) => (...args) => fn(...args, ...partials);
```

```js
const greet = (greeting, name) => greeting + ' ' + name + '!';
const greetJohn = partialRight(greet, 'John');
greetJohn('Hello'); // 'Hello John!'
```
