---
title: 数组转换为对象(Array to flags object)
tags: array,object
expertise: intermediate
author: chalarangelo
cover: blog_images/glass-blowing.jpg
firstSeen: 2022-04-12T05:00:00-04:00
---

# 将字符串数组转换为对象映射为真。
> Converts an array of strings into an object mapping to true.

- 使用 `Array.prototype.reduce()` 将数组转换为对象，其中每个数组值都用作值设置为 `true` 的键。

```js
const flags = arr => arr.reduce((acc, str) => ({...acc, [str]: true }), {});
```

```js
flags(['red', 'green']); // { red: true, green: true }
```
