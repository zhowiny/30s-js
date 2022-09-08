---
title: 前 n 个元素(First n elements)
tags: array
expertise: beginner
author: chalarangelo
cover: blog_images/digital-nomad-16.jpg
firstSeen: 2022-07-22T05:00:00-04:00
---

### 获取数组的前 n 个元素。
> Gets the first `n` elements of an array.

- 使用 `Array.prototype.slice()` 以 `0` 开始值和 `n` 结束值获取 `arr` 的前 `n` 个元素。

```js
const firstN = (arr, n) => arr.slice(0, n);
```

```js
firstN(['a', 'b', 'c', 'd'], 2); // ['a', 'b']
```
