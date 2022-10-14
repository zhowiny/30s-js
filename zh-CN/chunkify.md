---
title: 可迭代对象分割成块(Chunk iterable)
tags: function,generator,array
expertise: advanced
author: chalarangelo
cover: blog_images/cave-view.jpg
firstSeen: 2021-03-16T22:50:40+02:00
lastUpdated: 2021-03-16T22:50:40+02:00
---

# 将可迭代对象分块为指定大小的较小数组。
> Chunks an iterable into smaller arrays of a specified size.

- 在给定的可迭代对象上使用 `for...of` 循环，使用 `Array.prototype.push()` 将每个新值添加到当前的 `chunk`。
- 使用 `Array.prototype.length` 检查当前的 `chunk` 是否具有所需的 `size` 和 `yield` 值，如果是。
- 最后，使用 `Array.prototype.length` 检查最终的 `chunk` 和 `yield` 如果它非空。

```js
const chunkify = function* (itr, size) {
  let chunk = [];
  for (const v of itr) {
    chunk.push(v);
    if (chunk.length === size) {
      yield chunk;
      chunk = [];
    }
  }
  if (chunk.length) yield chunk;
};
```

```js
const x = new Set([1, 2, 1, 3, 4, 1, 2, 5]);
[...chunkify(x, 2)]; // [[1, 2], [3, 4], [5]]
```
