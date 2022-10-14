---
title: 对象转键值对数组(Object to pairs)
tags: object,array
expertise: intermediate
author: chalarangelo
cover: blog_images/purple-leaves.jpg
firstSeen: 2020-03-23T15:07:23+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 从对象或其他可迭代对象创建键值对数组的数组。
> Creates an array of key-value pair arrays from an object or other iterable.

- 检查 `Symbol.iterator` 是否已定义，如果是，则使用 `Array.prototype.entries()` 获取给定迭代的迭代器。
- 使用 `Array.from()` 将结果转换为键值对数组的数组。
- 如果没有为 `obj` 定义 `Symbol.iterator`，请改用 `Object.entries()`。

```js
const toPairs = obj =>
  obj[Symbol.iterator] instanceof Function && obj.entries instanceof Function
    ? Array.from(obj.entries())
    : Object.entries(obj);
```

```js
toPairs({ a: 1, b: 2 }); // [['a', 1], ['b', 2]]
toPairs([2, 4, 8]); // [[0, 2], [1, 4], [2, 8]]
toPairs('shy'); // [['0', 's'], ['1', 'h'], ['2', 'y']]
toPairs(new Set(['a', 'b', 'c', 'a'])); // [['a', 'a'], ['b', 'b'], ['c', 'c']]
```
