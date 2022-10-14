---
title: 幂集(Powerset)
tags: math,algorithm
expertise: beginner
cover: blog_images/new-plant.jpg
firstSeen: 2017-12-07T14:41:33+02:00
lastUpdated: 2021-09-27T15:27:07+02:00
---

# 返回给定数字数组的幂集。
> Returns the powerset of a given array of numbers.

- 使用 `Array.prototype.reduce()` 结合 `Array.prototype.map()` 来迭代元素并组合成一个包含所有组合的数组。
- [幂集(维基百科)](https://zh.wikipedia.org/zh-cn/%E5%86%AA%E9%9B%86)

```js
const powerset = arr =>
  arr.reduce((a, v) => a.concat(a.map(r => r.concat(v))), [[]]);
```

```js
powerset([1, 2]); // [[], [1], [2], [1, 2]]
```
