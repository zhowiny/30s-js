---
title: 将函数转换为可变参数函数(Convert function to variadic)
tags: function,array
expertise: intermediate
cover: blog_images/polar-bear.jpg
firstSeen: 2017-12-22T05:08:36+02:00
lastUpdated: 2021-06-13T13:50:25+03:00
---

### 将接受数组的函数更改为可变参数函数。
> Changes a function that accepts an array into a variadic function.

- 给定一个函数，返回一个闭包，它将所有输入收集到一个接受数组的函数中。

```js
const collectInto = fn => (...args) => fn(args);
```

```js
const Pall = collectInto(Promise.all.bind(Promise));
let p1 = Promise.resolve(1);
let p2 = Promise.resolve(2);
let p3 = new Promise(resolve => setTimeout(resolve, 2000, 3));
Pall(p1, p2, p3).then(console.log); // [1, 2, 3] (after about 2 seconds)
```
