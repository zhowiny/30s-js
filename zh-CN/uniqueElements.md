---
title: 数组中的唯一值(数组去重)(Unique values in array)
tags: array
expertise: beginner
cover: blog_images/architectural.jpg
firstSeen: 2018-01-17T19:02:49+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

### 查找数组中的所有唯一值。
> Finds all unique values in an array.

- 从给定的数组创建一个 `Set` 以丢弃重复的值。
- 使用扩展运算符 (`...`) 将其转换回数组。

```js
const uniqueElements = arr => [...new Set(arr)];
```

```js
uniqueElements([1, 2, 2, 3, 4, 4, 5]); // [1, 2, 3, 4, 5]
```
