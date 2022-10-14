---
title: 重新排列函数参数(Rearrange function arguments)
tags: function
expertise: intermediate
cover: blog_images/island-corridor.jpg
firstSeen: 2018-01-28T15:04:21+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 创建一个函数，该函数调用提供的函数，其参数根据指定的索引排列。
> Creates a function that invokes the provided function with its arguments arranged according to the specified indexes.

- 使用 `Array.prototype.map()` 根据 `indexes` 重新排序参数。
- 使用扩展运算符 (`...`) 将转换后的参数传递给 `fn`。

```js
const rearg = (fn, indexes) => (...args) => fn(...indexes.map(i => args[i]));
```

```js
var rearged = rearg(
  function(a, b, c) {
    return [a, b, c];
  },
  [2, 0, 1]
);
rearged('b', 'c', 'a'); // ['a', 'b', 'c']
```
