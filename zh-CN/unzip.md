---
title: 取消分组数组元素(Ungroup array elements)
tags: array
expertise: intermediate
cover: blog_images/glass-blowing.jpg
firstSeen: 2018-01-24T12:35:25+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

# 创建一个二维数组，取消由 [zip](./zip) 组合生成的数组中的元素。
> Creates an array of arrays, ungrouping the elements in an array produced by [zip](./zip).

- 使用 `Math.max()`、`Function.prototype.apply()` 获取数组中最长的子数组， `Array.prototype.map()` 使每个元素成为一个数组。
- 使用 `Array.prototype.reduce()` 和 `Array.prototype.forEach()` 将分组值映射到单个数组。

```js
const unzip = arr =>
  arr.reduce(
    (acc, val) => (val.forEach((v, i) => acc[i].push(v)), acc),
    Array.from({
      length: Math.max(...arr.map(x => x.length))
    }).map(x => [])
  );
```

```js
unzip([['a', 1, true], ['b', 2, false]]); // [['a', 'b'], [1, 2], [true, false]]
unzip([['a', 1, true], ['b', 2]]); // [['a', 'b'], [1, 2], [true]]
```
