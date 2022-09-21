---
title: 基于函数的数组中的唯一值(Unique values in array based on function)
tags: array
expertise: intermediate
cover: blog_images/sunrise-over-mountains.jpg
firstSeen: 2018-07-18T20:49:07+03:00
lastUpdated: 2021-10-13T19:29:39+02:00
---

### 根据提供的比较器函数查找数组的所有唯一值。
> Finds all unique values of an array, based on a provided comparator function.

- 使用 `Array.prototype.reduce()` 和 `Array.prototype.some()` 根据比较器函数 `fn` 创建一个仅包含每个值的第一次唯一出现的数组。
- 比较器函数有两个参数：被比较的两个元素的值。

```js
const uniqueElementsBy = (arr, fn) =>
  arr.reduce((acc, v) => {
    if (!acc.some(x => fn(v, x))) acc.push(v);
    return acc;
  }, []);
```

```js
uniqueElementsBy(
  [
    { id: 0, value: 'a' },
    { id: 1, value: 'b' },
    { id: 2, value: 'c' },
    { id: 1, value: 'd' },
    { id: 0, value: 'e' }
  ],
  (a, b) => a.id == b.id
); // [ { id: 0, value: 'a' }, { id: 1, value: 'b' }, { id: 2, value: 'c' } ]
```
