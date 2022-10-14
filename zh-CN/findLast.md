---
title: 查找最后一个匹配值(Find last matching value)
tags: array
expertise: beginner
cover: blog_images/misty-mountains.jpg
firstSeen: 2018-01-11T13:51:58+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 查找提供的函数为其返回真值的最后一个元素。
> Finds the last element for which the provided function returns a truthy value.

- 使用 `Array.prototype.filter()` 删除 `fn` 返回错误值的元素。
- 使用 `Array.prototype.pop()` 获取过滤后的数组中的最后一个元素。

```js
const findLast = (arr, fn) => arr.filter(fn).pop();
```

```js
findLast([1, 2, 3, 4], n => n % 2 === 1); // 3
```
