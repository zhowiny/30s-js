---
title: 函数执行频率(Hertz frequency of function)
tags: function
expertise: intermediate
unlisted: true
cover: blog_images/lake-runner.jpg
firstSeen: 2018-04-11T16:39:49+03:00
lastUpdated: 2021-01-04T13:04:15+02:00
---

# 测量每秒执行函数的次数（赫兹）。
> Measures the number of times a function is executed per second (hz/hertz).

- 使用 `performance.now()` 获取迭代循环前后的毫秒差，以计算执行函数 `iterations` 次所用的时间。
- 通过将毫秒转换为秒并将其除以经过的时间，返回每秒的周期数。
- 省略第二个参数，`iterations`，使用默认的 100 次迭代。
- [赫兹（维基百科）](https://zh.wikipedia.org/zh-cn/%E8%B5%AB%E5%85%B9)
- [赫兹（百度百科）](https://baike.baidu.com/item/%E8%B5%AB%E5%85%B9/7245576)

```js
const hz = (fn, iterations = 100) => {
  const before = performance.now();
  for (let i = 0; i < iterations; i++) fn();
  return (1000 * iterations) / (performance.now() - before);
};
```

```js
const numbers = Array(10000).fill().map((_, i) => i);

const sumReduce = () => numbers.reduce((acc, n) => acc + n, 0);
const sumForLoop = () => {
  let sum = 0;
  for (let i = 0; i < numbers.length; i++) sum += numbers[i];
  return sum;
};

Math.round(hz(sumReduce)); // 572
Math.round(hz(sumForLoop)); // 4784
```
