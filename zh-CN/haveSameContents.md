---
title: 检查数组是否具有相同的内容(Check if arrays have same contents)
tags: array
expertise: intermediate
author: chalarangelo
cover: blog_images/interior-15.jpg
firstSeen: 2020-01-05T21:40:39+02:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

# 无论顺序如何，检查两个数组是否包含相同的元素。
> Checks if two arrays contain the same elements regardless of order.

- 在从两个数组的值创建的 `Set` 上使用 `for...of` 循环。
- 使用 `Array.prototype.filter()` 比较两个数组中每个不同值的出现次数。
- 如果计数不匹配任何元素，则返回 `false`，否则返回 `true`。

```js
const haveSameContents = (a, b) => {
  for (const v of new Set([...a, ...b]))
    if (a.filter(e => e === v).length !== b.filter(e => e === v).length)
      return false;
  return true;
};
```

```js
haveSameContents([1, 2, 4], [2, 4, 1]); // true
```
