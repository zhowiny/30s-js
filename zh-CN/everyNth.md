---
title: 每个 `nth` 元素(Every nth element)
tags: array
expertise: beginner
cover: blog_images/dark-leaves-6.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-19T18:51:03+03:00
---

# 返回数组中的每个 `nth` 元素。
> Returns every `nth` element in an array.

- 使用 `Array.prototype.filter()` 创建一个新数组，其中包含给定数组的每个 `nth` 元素。

```js
const everyNth = (arr, nth) => arr.filter((e, i) => i % nth === nth - 1);
```

```js
everyNth([1, 2, 3, 4, 5, 6], 2); // [ 2, 4, 6 ]
```
