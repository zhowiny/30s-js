---
title: 从可变参数转换函数(Convert function from variadic)
tags: function
expertise: intermediate
cover: blog_images/tent-stars.jpg
firstSeen: 2017-12-22T04:33:57+02:00
lastUpdated: 2021-06-13T13:50:25+03:00
---

# 接受一个可变参数函数并返回一个接受参数数组的函数。
> Takes a variadic function and returns a function that accepts an array of arguments.

- 使用闭包和扩展运算符 (`...`) 将参数数组映射到函数的输入。

```js
const spreadOver = fn => argsArr => fn(...argsArr);
```

```js
const arrayMax = spreadOver(Math.max);
arrayMax([1, 2, 3]); // 3
```
