---
title: 数组中出现频率最高的元素(Most frequent element in array)
tags: array
expertise: intermediate
author: chalarangelo
cover: blog_images/clock.jpg
firstSeen: 2020-01-03T15:32:46+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

### 返回数组中出现频率最高的元素。
> Returns the most frequent element in an array.

- 使用 `Array.prototype.reduce()` 将唯一值映射到对象的键，每次遇到相同值时添加到现有键。
- 在结果上使用 `Object.entries()` 并结合 `Array.prototype.reduce()` 来获取数组中最频繁的值。

```js
const mostFrequent = arr =>
  Object.entries(
    arr.reduce((a, v) => {
      a[v] = a[v] ? a[v] + 1 : 1;
      return a;
    }, {})
  ).reduce((a, v) => (v[1] >= a[1] ? v : a), [null, 0])[0];
```

```js
mostFrequent(['a', 'b', 'a', 'c', 'a', 'a', 'b']); // 'a'
```
