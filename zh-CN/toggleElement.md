---
title: 切换数组中的元素(Toggle element in array)
tags: array
expertise: beginner
author: chalarangelo
cover: blog_images/digital-nomad-7.jpg
firstSeen: 2022-04-15T05:00:00-04:00
---

# 如果元素包含在数组中，则从数组中删除该元素，如果不包含，则将其推送到数组中。
> Removes an element from an array if it's included in the array, or pushes it to the array if it isn't.

- 使用 `Array.prototype.includes()` 检查给定元素是否在数组中。
- 使用 `Array.prototype.filter()` 删除数组中的元素。
- 如果元素不在数组中，则使用扩展运算符 (`...`) 推送该元素。

```js
const toggleElement = (arr, val) =>
  arr.includes(val) ? arr.filter(el => el !== val) : [...arr, val];

```

```js
toggleElement([1, 2, 3], 2); // [1, 3]
toggleElement([1, 2, 3], 4); // [1, 2, 3, 4]
```
