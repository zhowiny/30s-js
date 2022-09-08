---
title: 根据函数过滤唯一数组值(Filter unique array values based on function)
tags: array
expertise: intermediate
author: maciv
cover: blog_images/washed-ashore.jpg
firstSeen: 2020-11-02T19:41:07+02:00
lastUpdated: 2020-11-02T19:41:07+02:00
---

### 根据提供的比较器函数，创建一个过滤掉唯一值的数组。
> Creates an array with the unique values filtered out, based on a provided comparator function.

- 使用 `Array.prototype.filter()` 和 `Array.prototype.every()` 根据比较函数 `fn` 创建一个仅包含非唯一值的数组。
- 比较器函数有四个参数：被比较的两个元素的值及其索引。

```js
const filterUniqueBy = (arr, fn) =>
  arr.filter((v, i) => arr.some((x, j) => (i !== j) === fn(v, x, i, j)));
```

```js
filterUniqueBy(
  [
    { id: 0, value: 'a' },
    { id: 1, value: 'b' },
    { id: 2, value: 'c' },
    { id: 3, value: 'd' },
    { id: 0, value: 'e' }
  ],
  (a, b) => a.id == b.id
); // [ { id: 0, value: 'a' }, { id: 0, value: 'e' } ]
```
