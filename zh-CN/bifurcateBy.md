---
title: 基于函数将数组分组(Bifurcate array based on function)
tags: array
expertise: intermediate
cover: blog_images/canoe.jpg
firstSeen: 2018-02-14T12:13:07+02:00
lastUpdated: 2020-11-01T20:50:57+02:00
---

### 根据给定过滤函数的结果将值分成两组。
> Split values into two groups, based on the result of the given filtering function.

- 根据 `fn` 为每个元素返回的值，使用 `Array.prototype.reduce()` 和 `Array.prototype.push()` 将元素添加到组中。
- 如果 `fn` 返回任何元素的真值，则将其添加到第一组，否则将其添加到第二组。

```js
const bifurcateBy = (arr, fn) =>
  arr.reduce((acc, val, i) => (acc[fn(val, i) ? 0 : 1].push(val), acc), [
    [],
    [],
  ]);
```

```js
bifurcateBy(['beep', 'boop', 'foo', 'bar'], x => x[0] === 'b');
// [ ['beep', 'boop', 'bar'], ['foo'] ]
```
