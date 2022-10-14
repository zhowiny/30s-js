---
title: 从左侧删除数组元素(Drop list elements from the left)
tags: array
expertise: beginner
cover: blog_images/bridge-drop.jpg
firstSeen: 2018-01-26T12:23:18+02:00
lastUpdated: 2020-11-01T20:50:57+02:00
---

# 创建一个新数组，其中从左侧删除了 `n` 个元素。
> Creates a new array with `n` elements removed from the left.

- 使用 `Array.prototype.slice()` 从左侧删除指定数量的元素。
- 省略最后一个参数 `n` 以使用默认值 `1`。

```js
const drop = (arr, n = 1) => arr.slice(n);
```

```js
drop([1, 2, 3]); // [2, 3]
drop([1, 2, 3], 2); // [3]
drop([1, 2, 3], 42); // []
```
