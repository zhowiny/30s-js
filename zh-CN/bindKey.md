---
title: 将对象指定方法的上下文绑定到对象(Bind object method)
tags: function,object
expertise: advanced
cover: blog_images/oven-paddle.jpg
firstSeen: 2018-01-24T14:22:43+02:00
lastUpdated: 2020-10-18T23:04:45+03:00
---
### 创建一个函数，该函数在对象的给定键处调用该方法，可选择将任何其他提供的参数添加到参数中。
> Creates a function that invokes the method at a given key of an object, optionally prepending any additional supplied parameters to the arguments.

- 返回一个使用 `Function.prototype.apply()` 将 `context[fn]` 绑定到 `context` 的 `function`。
- 使用扩展运算符 (`...`) 将任何其他提供的参数添加到参数中。

```js
const bindKey = (context, fn, ...boundArgs) => (...args) =>
  context[fn].apply(context, [...boundArgs, ...args]);
```

```js
// before
const freddy = {
  user: 'fred',
  greet: function(greeting, punctuation) {
    return greeting + ' ' + this.user + punctuation;
  }
};
const freddyBound = freddy.greet;
console.log(freddyBound('hi', '!')); // 'hi undefined!'
```

```js
// after
const freddy = {
  user: 'fred',
  greet: function(greeting, punctuation) {
    return greeting + ' ' + this.user + punctuation;
  }
};
const freddyBound = bindKey(freddy, 'greet');
console.log(freddyBound('hi', '!')); // 'hi fred!'
```
