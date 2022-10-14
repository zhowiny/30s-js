---
title: 数组的尾部(Array tail)
tags: array
expertise: beginner
cover: blog_images/waves-from-above.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 返回数组中除第一个元素之外的所有元素。
> Returns all elements in an array except for the first one.

- 如果 `Array.prototype.length` 大于 `1`，则使用 `Array.prototype.slice()` 返回不包含第一个元素的数组。
- 否则，返回整个数组。

```js
const tail = arr => (arr.length > 1 ? arr.slice(1) : arr);
```

```js
tail([1, 2, 3]); // [2, 3]
tail([1]); // [1]
```
