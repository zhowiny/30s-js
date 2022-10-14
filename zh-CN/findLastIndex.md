---
title: 查找最后一个匹配索引(Find last matching index)
tags: array
expertise: intermediate
cover: blog_images/taking-photos.jpg
firstSeen: 2018-01-24T13:01:51+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 查找提供的函数为其返回真值的最后一个元素的索引。
> Finds the index of the last element for which the provided function returns a truthy value.

- 使用 `Array.prototype.map()` 将每个元素映射到具有其索引和值的数组。
- 使用 `Array.prototype.filter()` 删除 `fn` 返回错误值的元素
- 使用 `Array.prototype.pop()` 获取过滤后的数组中的最后一个元素。
- 如果没有匹配的元素，则返回 `-1`。

```js
const findLastIndex = (arr, fn) =>
  (arr
    .map((val, i) => [i, val])
    .filter(([i, val]) => fn(val, i, arr))
    .pop() || [-1])[0];
```

```js
findLastIndex([1, 2, 3, 4], n => n % 2 === 1); // 2 (值为 3 的索引)
findLastIndex([1, 2, 3, 4], n => n === 5); // -1 (未找到时的默认值)
```
