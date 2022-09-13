---
title: K-近邻算法(K-nearest neighbors)
tags: algorithm,array
expertise: advanced
author: chalarangelo
cover: blog_images/building-blocks.jpg
firstSeen: 2020-12-28T16:31:43+02:00
lastUpdated: 2021-10-13T19:29:39+02:00
---

### 使用 [k-nearest neighbors](https://en.wikipedia.org/wiki/K-nearest_neighbors_algorithm) 算法相对于标记数据集对数据点进行分类。
> Classifies a data point relative to a labelled data set, using the [k-nearest neighbors](https://en.wikipedia.org/wiki/K-nearest_neighbors_algorithm) algorithm.

- 使用 `Array.prototype.map()` 将 `data` 映射到对象。 每个对象包含元素到 `point` 的欧几里德距离，使用 `Math.hypot()`、 `Object.keys()` 及其 `lebel` 计算。
- 使用 `Array.prototype.sort()` 和 `Array.prototype.slice()` 获取 `point` 的 `k` 最近邻。
- 将 `Array.prototype.reduce()` 与 `Object.keys()` 和 `Array.prototype.indexOf()` 结合使用，找出其中出现频率最高的 `label`。
- [K-近邻算法(维基百科)](https://zh.wikipedia.org/zh-cn/K-%E8%BF%91%E9%82%BB%E7%AE%97%E6%B3%95)
- [邻近算法(百度科)](https://baike.baidu.com/item/%E9%82%BB%E8%BF%91%E7%AE%97%E6%B3%95/1151153)

```js
const kNearestNeighbors = (data, labels, point, k = 3) => {
  const kNearest = data
    .map((el, i) => ({
      dist: Math.hypot(...Object.keys(el).map(key => point[key] - el[key])),
      label: labels[i]
    }))
    .sort((a, b) => a.dist - b.dist)
    .slice(0, k);

  return kNearest.reduce(
    (acc, { label }, i) => {
      acc.classCounts[label] =
        Object.keys(acc.classCounts).indexOf(label) !== -1
          ? acc.classCounts[label] + 1
          : 1;
      if (acc.classCounts[label] > acc.topClassCount) {
        acc.topClassCount = acc.classCounts[label];
        acc.topClass = label;
      }
      return acc;
    },
    {
      classCounts: {},
      topClass: kNearest[0].label,
      topClassCount: 0
    }
  ).topClass;
};
```

```js
const data = [[0, 0], [0, 1], [1, 3], [2, 0]];
const labels = [0, 1, 1, 0];

kNearestNeighbors(data, labels, [1, 2], 2); // 1
kNearestNeighbors(data, labels, [1, 0], 2); // 0
```
