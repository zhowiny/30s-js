---
title: 在数组指定索引位置插入值(Insert value at array index)
tags: array
expertise: intermediate
author: chalarangelo
cover: blog_images/messy-papers.jpg
firstSeen: 2020-05-22T09:07:35+03:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 改变原始数组以在指定索引之后插入给定值。
> Mutates the original array to insert the given values after the specified index.

- 使用具有适当索引和删除计数为 0 的 `Array.prototype.splice()`，分散要插入的给定值。

```js
const insertAt = (arr, i, ...v) => {
  arr.splice(i + 1, 0, ...v);
  return arr;
};
```

```js
let myArray = [1, 2, 3, 4];
insertAt(myArray, 2, 5); // myArray = [1, 2, 3, 5, 4]

let otherArray = [2, 10];
insertAt(otherArray, 0, 4, 6, 8); // otherArray = [2, 4, 6, 8, 10]
```
