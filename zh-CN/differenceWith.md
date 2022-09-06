---
title: 基于函数的数组差异(Array difference based on function)
tags: array
expertise: intermediate
cover: blog_images/folded-map.jpg
firstSeen: 2017-12-19T12:32:24+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 从数组中过滤出比较器函数不返回 `true` 的所有值。
> Filters out all values from an array for which the comparator function does not return `true`.

- 使用 `Array.prototype.filter()` 和 `Array.prototype.findIndex()` 找到合适的值。
- 省略最后一个参数 `comp`，以使用默认的严格相等比较器。

```js
const differenceWith = (arr, val, comp = (a, b) => a === b) =>
  arr.filter(a => val.findIndex(b => comp(a, b)) === -1);
```

```js
differenceWith(
  [1, 1.2, 1.5, 3, 0],
  [1.9, 3, 0],
  (a, b) => Math.round(a) === Math.round(b)
); // [1, 1.2]
differenceWith([1, 1.2, 1.3], [1, 1.3, 1.5]); // [1.2]
```
