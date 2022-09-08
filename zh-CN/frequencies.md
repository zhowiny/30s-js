---
title: 值出现的次数(Value frequencies)
tags: array,object
expertise: intermediate
author: chalarangelo
cover: blog_images/tropical-waterfall.jpg
firstSeen: 2020-01-03T15:32:35+02:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 创建一个对象，其中数组的唯一值作为键，它们的频率作为值。
> Creates an object with the unique values of an array as keys and their frequencies as the values.

- 使用 `Array.prototype.reduce()` 将唯一值映射到对象的键，每次遇到相同值时添加到现有键。

```js
const frequencies = arr =>
  arr.reduce((a, v) => {
    a[v] = a[v] ? a[v] + 1 : 1;
    return a;
  }, {});
```

```js
frequencies(['a', 'b', 'a', 'c', 'a', 'a', 'b']); // { a: 4, b: 2, c: 1 }
frequencies([...'ball']); // { b: 1, a: 1, l: 2 }
```
