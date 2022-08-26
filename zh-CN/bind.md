---
title: 绑定函数上下文(Bind function context)
tags: function,object
expertise: advanced
cover: blog_images/tranquility.jpg
firstSeen: 2018-01-24T14:14:49+02:00
lastUpdated: 2020-10-18T23:04:45+03:00
---

### 创建一个使用给定上下文调用 `fn` 的函数，可选择将任何其他提供的参数添加到参数中。
> Creates a function that invokes `fn` with a given context, optionally prepending any additional supplied parameters to the arguments.

- 返回一个使用 `Function.prototype.apply()` 将给定 `context` 应用到 `fn` 的`function`。
- 使用扩展运算符 (`...`) 将任何其他提供的参数添加到参数中。

```js
const bind = (fn, context, ...boundArgs) => (...args) =>
  fn.apply(context, [...boundArgs, ...args]);
```

```js
function greet(greeting, punctuation) {
  return greeting + ' ' + this.user + punctuation;
}
const freddy = { user: 'fred' };
const freddyBound = bind(greet, freddy);
console.log(freddyBound('hi', '!')); // 'hi fred!'
```
