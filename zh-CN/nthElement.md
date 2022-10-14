---
title: 第 N 个元素(Nth element)
tags: array
expertise: beginner
cover: blog_images/laptop-plants.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

# 返回数组的第 n 个元素。
> Returns the nth element of an array.

- 使用 `Array.prototype.slice()` 获取包含第 n 个元素的数组。
- 如果索引超出范围，则返回 `undefined`。
- 省略第二个参数 `n`，以获取数组的第一个元素。

```js
const nthElement = (arr, n = 0) =>
  (n === -1 ? arr.slice(n) : arr.slice(n, n + 1))[0];
```

```js
nthElement(['a', 'b', 'c'], 1); // 'b'
nthElement(['a', 'b', 'b'], -3); // 'a'
```
