---
title: 根据函数过滤非唯一数组值(Filter non-unique array values based on function)
tags: array
expertise: intermediate
cover: blog_images/digital-nomad-16.jpg
firstSeen: 2018-07-18T20:40:53+03:00
lastUpdated: 2020-11-02T19:40:27+02:00
---

### 根据提供的比较器函数，创建一个过滤掉非唯一值的数组。
> Creates an array with the non-unique values filtered out, based on a provided comparator function.

- 使用 `Array.prototype.filter()` 和 `Array.prototype.every()` 根据比较器函数 `fn` 创建一个仅包含唯一值的数组。
- 比较器函数有四个参数：被比较的两个元素的值及其索引。

```js
const filterNonUniqueBy = (arr, fn) =>
  arr.filter((v, i) => arr.every((x, j) => (i === j) === fn(v, x, i, j)));
```

```js
filterNonUniqueBy(
  [
    { id: 0, value: 'a' },
    { id: 1, value: 'b' },
    { id: 2, value: 'c' },
    { id: 1, value: 'd' },
    { id: 0, value: 'e' }
  ],
  (a, b) => a.id === b.id
); // [ { id: 2, value: 'c' } ]
```
