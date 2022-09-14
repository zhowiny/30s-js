---
title: 第 N 个参数(Nth argument)
tags: function
expertise: beginner
cover: blog_images/mug-flower-book.jpg
firstSeen: 2018-01-23T21:27:37+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 创建一个函数，该函数在索引 `n` 处获取参数。
> Creates a function that gets the argument at index `n`.

- 使用 `Array.prototype.slice()` 在索引 `n` 处获取所需的参数。
- 如果 `n` 为负数，则返回倒数第 n 个参数。

```js
const nthArg = n => (...args) => args.slice(n)[0];
```

```js
const third = nthArg(2);
third(1, 2, 3); // 3
third(1, 2); // undefined
const last = nthArg(-1);
last(1, 2, 3, 4, 5); // 5
```
