---
title: 满足条件时取出数组元素(Remove list elements while condition is met)
tags: array
expertise: intermediate
cover: blog_images/colors-mural.jpg
firstSeen: 2018-01-26T12:55:31+02:00
lastUpdated: 2020-11-29T12:04:53+02:00
---

# 取出数组中的元素，直到传递的函数返回 `false`。返回取出的元素。
> Removes elements in an array until the passed function returns `false`.
> Returns the removed elements.

- 遍历数组，使用 `Array.prototype.entries()` 上的 `for...of` 循环，直到函数的返回值是 `false`。
- 使用 `Array.prototype.slice()` 返回取出的元素。
- 回调函数 `fn` 接受单个参数，即元素的值。

```js
const takeWhile = (arr, fn) => {
  for (const [i, val] of arr.entries()) if (!fn(val)) return arr.slice(0, i);
  return arr;
};
```

```js
takeWhile([1, 2, 3, 4], n => n < 3); // [1, 2]
```
