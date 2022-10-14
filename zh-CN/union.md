---
title: 数组的并集(Array union)
tags: array
expertise: beginner
cover: blog_images/yellow-white-mug-2.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

# 至少返回一次存在于两个数组中的任何一个中的每个元素。
> Returns every element that exists in any of the two arrays at least once.

- 创建一个包含所有值a和b的集合，并将其转换为数组。

```js
const union = (a, b) => Array.from(new Set([...a, ...b]));
```

```js
union([1, 2, 3], [4, 3, 2]); // [1, 2, 3, 4]
```
