---
title: 数组包含在其他数组中(Array is contained in other array)
tags: array
expertise: intermediate
author: chalarangelo
cover: blog_images/island-corridor.jpg
firstSeen: 2020-01-05T21:40:51+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 检查第一个数组的元素是否包含在第二个数组中，无论顺序如何。
> Checks if the elements of the first array are contained in the second one regardless of order.

- 在从第一个数组创建的 `Set` 上使用 `for...of` 循环。
- 使用 `Array.prototype.some()` 检查是否所有不同的值都包含在第二个数组中。
- 使用 `Array.prototype.filter()` 比较两个数组中每个不同值的出现次数。
- 如果第一个数组中任何元素的计数大于第二个数组，则返回 `false`，否则返回 `true`。

```js
const isContainedIn = (a, b) => {
  for (const v of new Set(a)) {
    if (
      !b.some(e => e === v) ||
      a.filter(e => e === v).length > b.filter(e => e === v).length
    )
      return false;
  }
  return true;
};
```

```js
isContainedIn([1, 4], [2, 4, 1]); // true
```
