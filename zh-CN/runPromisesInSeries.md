---
title: 连续运行 Promise(Run promises in series)
tags: function,promise
expertise: intermediate
cover: blog_images/sail-away.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 连续运行一系列 Promise。
> Runs an array of promises in series.

- 使用 `Array.prototype.reduce()` 创建一个 Promise 链，其中每个 Promise 在解决时返回下一个 Promise。

```js
const runPromisesInSeries = ps =>
  ps.reduce((p, next) => p.then(next), Promise.resolve());
```

```js
const delay = d => new Promise(r => setTimeout(r, d));
runPromisesInSeries([() => delay(1000), () => delay(2000)]);
// 依次执行每个promise，总共需要3秒完成
```
