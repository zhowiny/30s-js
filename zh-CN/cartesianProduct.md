---
title: 笛卡尔积(乘积)(Cartesian product)
tags: math,array
expertise: beginner
author: maciv
cover: blog_images/sail-away.jpg
firstSeen: 2020-12-28T20:23:47+02:00
lastUpdated: 2020-12-29T12:31:43+02:00
---

# 计算两个数组的笛卡尔积。
> Calculates the cartesian product of two arrays.

- 使用 `Array.prototype.reduce()`、`Array.prototype.map()` 和扩展运算符 (`...`) 从两个数组中生成所有可能的元素对。

```js
const cartesianProduct = (a, b) =>
  a.reduce((p, x) => [...p, ...b.map(y => [x, y])], []);
```

```js
cartesianProduct(['x', 'y'], [1, 2]);
// [['x', 1], ['x', 2], ['y', 1], ['y', 2]]
```


> [笛卡尔积(百度百科)](https://baike.baidu.com/item/%E7%AC%9B%E5%8D%A1%E5%B0%94%E4%B9%98%E7%A7%AF/6323173)
>
> [笛卡尔积(维基百科)](https://zh.wikipedia.org/wiki/%E7%AC%9B%E5%8D%A1%E5%84%BF%E7%A7%AF)

