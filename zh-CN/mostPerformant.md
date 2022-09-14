---
title: 最高性能的函数(Most performant function)
tags: function
expertise: advanced
cover: blog_images/lake-runner.jpg
firstSeen: 2018-02-14T13:38:45+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 返回执行最快的函数数组中函数的索引。
> Returns the index of the function in an array of functions which executed the fastest.

- 使用 `Array.prototype.map()` 生成一个数组，其中每个值是在 `iterations` 次之后执行函数所花费的总时间。
- 使用前后 `performance.now()` 值的差异来获得高度准确的总时间（以毫秒为单位）。
- 使用 `Math.min()` 查找最短执行时间，并返回与性能最高的函数的索引相对应的最短时间的索引。
- 省略第二个参数，`iterations`，使用默认的 `10000` 次迭代。
- 迭代次数越多，结果越可靠，但需要的时间越长。

```js
const mostPerformant = (fns, iterations = 10000) => {
  const times = fns.map(fn => {
    const before = performance.now();
    for (let i = 0; i < iterations; i++) fn();
    return performance.now() - before;
  });
  return times.indexOf(Math.min(...times));
};
```

```js
mostPerformant([
  () => {
    // 遍历整个数组, 再返回 `false`
    [1, 2, 3, 4, 5, 6, 7, 8, 9, '10'].every(el => typeof el === 'number');
  },
  () => {
    // 只需要到达索引 `1`, 返回 `false`
    [1, '2', 3, 4, 5, 6, 7, 8, 9, 10].every(el => typeof el === 'number');
  }
]); // 1
```
