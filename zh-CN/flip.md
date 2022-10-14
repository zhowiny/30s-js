---
title: 翻转函数参数(Flip function arguments)
tags: function
expertise: intermediate
cover: blog_images/interior-11.jpg
firstSeen: 2017-12-22T02:42:15+02:00
lastUpdated: 2021-06-13T13:50:25+03:00
---

# 将函数作为参数，然后将第一个参数作为最后一个参数。
> Takes a function as an argument, then makes the first argument the last.

- 使用参数解构和带有可变参数的闭包。
- 使用扩展运算符 (`...`) 拼接第一个参数，使其成为最后一个参数，然后再应用其余参数。

```js
const flip = fn => (first, ...rest) => fn(...rest, first);
```

```js
let a = { name: 'John Smith' };
let b = {};
const mergeFrom = flip(Object.assign);
let mergePerson = mergeFrom.bind(null, a);
mergePerson(b); // == b
b = {};
Object.assign(b, a); // == b
```
