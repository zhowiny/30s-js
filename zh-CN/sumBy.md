---
title: 映射数组总和(Mapped array sum)
tags: math,array
expertise: intermediate
cover: blog_images/avocado-slices.jpg
firstSeen: 2018-01-11T12:25:54+02:00
lastUpdated: 2020-11-03T22:11:18+02:00
---

### 在使用提供的函数将每个元素映射到一个值之后，计算数组的总和。
> Calculates the sum of an array, after mapping each element to a value using the provided function.

- 使用 `Array.prototype.map()` 将每个元素映射到 `fn` 返回的值。
- 使用 `Array.prototype.reduce()` 将每个值添加到累加器，初始化为 `0`。

```js
const sumBy = (arr, fn) =>
  arr
    .map(typeof fn === 'function' ? fn : val => val[fn])
    .reduce((acc, val) => acc + val, 0);
```

```js
sumBy([{ n: 4 }, { n: 2 }, { n: 8 }, { n: 6 }], x => x.n); // 20
sumBy([{ n: 4 }, { n: 2 }, { n: 8 }, { n: 6 }], 'n'); // 20
```
