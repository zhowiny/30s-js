---
title: 没有最后一个元素的数组(Array without last element)
tags: array
expertise: beginner
cover: blog_images/red-light.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-11-03T21:46:13+02:00
---

# 返回数组中除最后一个元素之外的所有元素。
> Returns all the elements of an array except the last one.

- 使用 `Array.prototype.slice()` 返回数组中除最后一个元素之外的所有元素。

```js
const initial = arr => arr.slice(0, -1);
```

```js
initial([1, 2, 3]); // [1, 2]
```
