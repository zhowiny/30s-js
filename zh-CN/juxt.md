---
title: 并列函数(Juxtapose functions)
tags: function
expertise: advanced
cover: blog_images/colorful-plastic.jpg
firstSeen: 2020-05-20T19:58:39+03:00
lastUpdated: 2020-10-20T23:29:39+03:00
---

# 将几个函数作为参数并返回一个函数，该函数是这些函数的并列。
> Takes several functions as argument and returns a function that is the juxtaposition of those functions.

- 使用 `Array.prototype.map()` 返回一个 `fn`，它可以采用可变数量的 `args`。
- 当 `fn` 被调用时，返回一个数组，其中包含将每个 `fn` 应用于 `args` 的结果。

```js
const juxt = (...fns) => (...args) => [...fns].map(fn => [...args].map(fn));
```

```js
juxt(
  x => x + 1,
  x => x - 1,
  x => x * 10
)(1, 2, 3); // [[2, 3, 4], [0, 1, 2], [10, 20, 30]]
juxt(
  s => s.length,
  s => s.split(' ').join('-')
)('30 seconds of code'); // [[18], ['30-seconds-of-code']]
```
