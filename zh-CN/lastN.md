---
title: 最后 n 个元素(Last n elements)
tags: array
expertise: beginner
author: chalarangelo
cover: blog_images/interior-5.jpg
firstSeen: 2022-07-23T05:00:00-04:00
---

### 获取数组的最后 `n` 个元素。
> Gets the last `n` elements of an array.

- 使用起始值为 `-n` 的 `Array.prototype.slice()` 来获取 `arr` 的最后 `n` 个元素。

```js
const lastN = (arr, n) => arr.slice(-n);
```

```js
lastN(['a', 'b', 'c', 'd'], 2); // ['c', 'd']
```
