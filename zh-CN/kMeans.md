---
title: k-均值算法(K-means clustering)
tags: algorithm,array
expertise: advanced
author: chalarangelo
cover: blog_images/antelope.jpg
firstSeen: 2020-12-28T15:38:40+02:00
lastUpdated: 2020-12-29T16:32:46+02:00
---

### 使用 [k-means clustering](https://en.wikipedia.org/wiki/K-means_clustering) 算法将给定数据分组到 `k` 个集群中。
> Groups the given data into `k` clusters, using the [k-means clustering](https://en.wikipedia.org/wiki/K-means_clustering) algorithm.

- 使用 `Array.from()` 和 `Array.prototype.slice()` 为集群 `centroids`、`distances` 和 `classes` 初始化适当的变量。
- 只要上一次迭代中有变化，就使用 `while` 循环重复分配和更新步骤，如 `itr` 所示。
- 使用 `Math.hypot()`、`Object.keys()` 和 `Array.prototype.map()` 计算每个数据点和质心(聚类中心)之间的欧几里得距离。
- 使用 `Array.prototype.indexOf()` 和 `Math.min()` 找到最近的质心。
- 使用 `Array.from()` 和 `Array.prototype.reduce()`，以及 `parseFloat()` 和 `Number.prototype.toFixed()` 来计算新的质心。
- [k-平均演算法(维基百科)](https://zh.wikipedia.org/wiki/K-%E5%B9%B3%E5%9D%87%E7%AE%97%E6%B3%95)
- [k均值聚类算法(百度百科)](https://baike.baidu.com/item/K%E5%9D%87%E5%80%BC%E8%81%9A%E7%B1%BB%E7%AE%97%E6%B3%95/15779627)

```js
const kMeans = (data, k = 1) => {
  const centroids = data.slice(0, k);
  const distances = Array.from({ length: data.length }, () =>
    Array.from({ length: k }, () => 0)
  );
  const classes = Array.from({ length: data.length }, () => -1);
  let itr = true;

  while (itr) {
    itr = false;

    for (let d in data) {
      for (let c = 0; c < k; c++) {
        distances[d][c] = Math.hypot(
          ...Object.keys(data[0]).map(key => data[d][key] - centroids[c][key])
        );
      }
      const m = distances[d].indexOf(Math.min(...distances[d]));
      if (classes[d] !== m) itr = true;
      classes[d] = m;
    }

    for (let c = 0; c < k; c++) {
      centroids[c] = Array.from({ length: data[0].length }, () => 0);
      const size = data.reduce((acc, _, d) => {
        if (classes[d] === c) {
          acc++;
          for (let i in data[0]) centroids[c][i] += data[d][i];
        }
        return acc;
      }, 0);
      for (let i in data[0]) {
        centroids[c][i] = parseFloat(Number(centroids[c][i] / size).toFixed(2));
      }
    }
  }

  return classes;
};
```

```js
kMeans([[0, 0], [0, 1], [1, 3], [2, 0]], 2); // [0, 1, 1, 0]
```
