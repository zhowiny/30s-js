---
title: 扁平化数组(Flatten array)
tags: array,recursion
expertise: intermediate
cover: blog_images/green-plant.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 将数组展平到指定的深度。
> Flattens an array up to the specified depth.

- 使用递归，对于每个深度级别将 `depth` 递减`1`。
- 使用 `Array.prototype.reduce()` 和 `Array.prototype.concat()` 来合并元素或数组。
- 基本情况，对于 `depth` 等于 `1` 停止递归。
- 省略第二个参数 `depth`，仅展平到 `1` 的深度（单展平）。
- **注:** [`Array.prototype.flat()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/flat)

```js
const flatten = (arr, depth = 1) =>
  arr.reduce(
    (a, v) =>
      a.concat(depth > 1 && Array.isArray(v) ? flatten(v, depth - 1) : v),
    []
  );
```

```js
flatten([1, [2], 3, 4]); // [1, 2, 3, 4]
flatten([1, [2, [3, [4, 5], 6], 7], 8], 2); // [1, 2, 3, [4, 5], 6, 7, 8]
```
