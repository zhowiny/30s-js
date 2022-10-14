---
title: 加权抽样(Weighted sample)
tags: array,random
expertise: advanced
author: chalarangelo
cover: blog_images/digital-nomad-14.jpg
firstSeen: 2019-12-31T11:34:26+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

# 从数组中获取一个随机元素，使用提供的 `weights` 作为每个元素的概率。
> Gets a random element from an array, using the provided `weights` as the probabilities for each element.

- 使用 `Array.prototype.reduce()` 为 `weights` 中的每个值创建一个部分和数组。
- 使用 `Math.random()` 生成一个随机数，并使用 `Array.prototype.findIndex()` 根据之前生成的数组找到正确的索引。
- 最后，使用生成的索引返回 `arr` 的元素。

```js
const weightedSample = (arr, weights) => {
  let roll = Math.random();
  return arr[
    weights
      .reduce(
        (acc, w, i) => (i === 0 ? [w] : [...acc, acc[acc.length - 1] + w]),
        []
      )
      .findIndex((v, i, s) => roll >= (i === 0 ? 0 : s[i - 1]) && roll < v)
  ];
};
```

```js
weightedSample([3, 7, 9, 11], [0.1, 0.2, 0.6, 0.1]); // 9
```
