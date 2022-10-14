---
title: 数组最后一个元素(Last array element)
tags: array
expertise: beginner
cover: blog_images/white-laptop.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 返回数组中的最后一个元素。
> Returns the last element in an array.

- 检查 `arr` 是否真实且具有 `length` 属性。
- 使用 `Array.prototype.length` 计算给定数组的最后一个元素的索引并返回它，否则返回 `undefined`。

```js
const last = arr => (arr && arr.length ? arr[arr.length - 1] : undefined);
```

```js
last([1, 2, 3]); // 3
last([]); // undefined
last(null); // undefined
last(undefined); // undefined
```
