---
title: 偏移数组元素(Offset array elements)
tags: array
expertise: beginner
cover: blog_images/interior-10.jpg
firstSeen: 2018-04-10T19:07:50+03:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

# 将指定数量的元素移动到数组的末尾。
> Moves the specified amount of elements to the end of the array.

- 使用 `Array.prototype.slice()` 两次获取指定索引之后的元素和之前的元素。
- 使用扩展运算符 (`...`) 将两者组合成一个数组。
- 如果 `offset` 为负数，元素将从头移动到头。

```js
const offset = (arr, offset) => [...arr.slice(offset), ...arr.slice(0, offset)];
```

```js
offset([1, 2, 3, 4, 5], 2); // [3, 4, 5, 1, 2]
offset([1, 2, 3, 4, 5], -2); // [4, 5, 1, 2, 3]
```
