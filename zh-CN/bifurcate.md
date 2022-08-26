---
title: 基于值将数组分组(Bifurcate array based on values)
tags: array
expertise: intermediate
cover: blog_images/two-cities.jpg
firstSeen: 2018-02-14T12:13:07+02:00
lastUpdated: 2020-11-01T20:50:57+02:00
---

### 根据给定的 `filter` 数组，将值分成两组。
> Splits values into two groups, based on the result of the given `filter` array.

- 使用 `Array.prototype.reduce()` 和 `Array.prototype.push()` 根据 `filter` 将元素添加到组中。
- 如果 `filter` 对任何元素都有真值，则将其添加到第一组，否则将其添加到第二组。

```js
const bifurcate = (arr, filter) =>
  arr.reduce((acc, val, i) => (acc[filter[i] ? 0 : 1].push(val), acc), [
    [],
    [],
  ]);
```

```js
bifurcate(['beep', 'boop', 'foo', 'bar'], [true, true, false, true]);
// [ ['beep', 'boop', 'bar'], ['foo'] ]
```
