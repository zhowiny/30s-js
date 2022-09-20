---
title: 数组的相似度(交集)(Array similarity)
tags: array,math
expertise: beginner
cover: blog_images/dark-leaves-5.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 返回出现在两个数组中的元素数组。
> Returns an array of elements that appear in both arrays.

- 使用 `Array.prototype.includes()` 来确定不属于 `values` 的值。
- 使用 `Array.prototype.filter()` 删除它们。

```js
const similarity = (arr, values) => arr.filter(v => values.includes(v));
```

```js
similarity([1, 2, 3], [1, 2, 4]); // [1, 2]
```
