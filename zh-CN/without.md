---
title: 过滤掉匹配的数组元素(Filter out matching array elements)
tags: array
expertise: beginner
cover: blog_images/dying-flowers.jpg
firstSeen: 2017-12-15T09:35:30+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

# 过滤出具有指定值之一的数组元素。
> Filters out the elements of an array that have one of the specified values.

- 使用 `Array.prototype.includes()` 查找要排除的值。
- 使用 `Array.prototype.filter()` 创建一个不包括它们的数组。

```js
const without = (arr, ...args) => arr.filter(v => !args.includes(v));
```

```js
without([2, 1, 2, 3], 1, 2); // [3]
```
