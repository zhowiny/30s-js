---
title: 根据函数取消分组数组元素(Ungroup array elements based on function)
tags: array
expertise: advanced
cover: blog_images/coconuts.jpg
firstSeen: 2018-01-24T12:44:16+02:00
lastUpdated: 2022-01-23T13:18:50+03:00
---

# 创建一个元素数组，将由 [zip](./zip) 生成的数组中的元素取消分组并应用提供的函数。
> Creates an array of elements, ungrouping the elements in an array produced by [zip](./zip) and applying the provided function.

- 使用 `Math.max()` 和扩展运算符 (`...`) 获取数组中最长的子数组，`Array.prototype.map()` 使每个元素成为一个数组。
- 使用 `Array.prototype.reduce()` 和 `Array.prototype.forEach()` 将分组值映射到单个数组。
- 使用 `Array.prototype.map()` 和扩展运算符 (`...`) 将 `fn` 应用于每个单独的元素组。

```js
const unzipWith = (arr, fn) =>
  arr
    .reduce(
      (acc, val) => (val.forEach((v, i) => acc[i].push(v)), acc),
      Array.from({
        length: Math.max(...arr.map(x => x.length))
      }).map(x => [])
    )
    .map(val => fn(...val));
```

```js
unzipWith(
  [
    [1, 10, 100],
    [2, 20, 200],
  ],
  (...args) => args.reduce((acc, v) => acc + v, 0)
);
// [3, 30, 300]
```
