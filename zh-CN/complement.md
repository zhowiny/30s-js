---
title: 逻辑非(Logical complement)
tags: function,logic
expertise: beginner
cover: blog_images/flower-portrait-10.jpg
firstSeen: 2020-05-13T11:28:33+03:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

### 返回一个函数，它是给定函数 `fn` 的逻辑非。
> Returns a function that is the logical complement of the given function, `fn`.

- 在使用任何提供的 `args` 调用 `fn` 的结果上使用逻辑非 (`!`) 运算符。

```js
const complement = fn => (...args) => !fn(...args);
```

```js
const isEven = num => num % 2 === 0;
const isOdd = complement(isEven);
isOdd(2); // false
isOdd(3); // true
```
