---
title: 从数组中删除匹配的元素(Remove matching elements from array)
tags: array
expertise: intermediate
cover: blog_images/highlands.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 通过删除给定函数返回 `false` 的元素来改变数组。
> Mutates an array by removing elements for which the given function returns `false`.

- 使用 `Array.prototype.filter()` 查找返回真值的数组元素。
- 使用 `Array.prototype.reduce()` 删除使用 `Array.prototype.splice()` 的元素。
- 使用三个参数（值、索引、数组）调用回调函数。

```js

const remove = (arr, func) =>
  Array.isArray(arr)
    ? arr.filter(func).reduce((acc, val) => {
      arr.splice(arr.indexOf(val), 1);
      return acc.concat(val);
    }, [])
    : [];
```

```js
remove([1, 2, 3, 4], n => n % 2 === 0); // [2, 4]
```
