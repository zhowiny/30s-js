---
title: 函数花费的时间(Time taken by function)
tags: function
expertise: beginner
cover: blog_images/shelf-plant.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 测量函数执行所需的时间。
> Measures the time it takes for a function to execute.

- 使用 `console.time()` 和 `console.timeEnd()` 测量开始时间和结束时间之间的差异，以确定回调执行的时间。

```js
const timeTaken = callback => {
  console.time('timeTaken');
  const r = callback();
  console.timeEnd('timeTaken');
  return r;
};
```

```js
timeTaken(() => Math.pow(2, 10)); // 1024, (logged): timeTaken: 0.02099609375ms
```
