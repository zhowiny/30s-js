---
title: 不折叠数组(Unfold array)
tags: function,array
expertise: intermediate
cover: blog_images/dog-waiting.jpg
firstSeen: 2018-01-24T16:22:14+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 使用迭代器函数和初始值 `seed` 构建一个数组。
> Builds an array, using an iterator function and an initial seed value.

- 使用 `while` 循环和 `Array.prototype.push()` 重复调用该函数，直到它返回 `false`。
- 迭代器函数接受一个参数（`seed`）并且必须始终返回一个包含两个元素（[`value`, `nextSeed`]）或`false` 的数组以终止。

```js
const unfold = (fn, seed) => {
  let result = [],
    val = [null, seed];
  while ((val = fn(val[1]))) result.push(val[0]);
  return result;
};
```

```js
var f = n => (n > 50 ? false : [-n, n + 10]);
unfold(f, 10); // [-10, -20, -30, -40, -50]
```
