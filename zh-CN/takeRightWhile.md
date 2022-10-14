---
title: 满足条件时从末尾取出数组元素(Remove list elements from the end while condition is met)
tags: array
expertise: intermediate
cover: blog_images/beach-pineapple.jpg
firstSeen: 2018-01-26T12:55:31+02:00
lastUpdated: 2020-11-29T12:04:53+02:00
---

# 从数组末尾取出元素，直到传递的函数返回 `false`。返回取出的元素。
> Removes elements from the end of an array until the passed function returns `false`.
> Returns the removed elements.

- 使用展开运算符 (`...`) 和 `Array.prototype.reverse()` 创建数组的反向副本。
- 遍历反向副本，使用 `Array.prototype.entries()` 上的 `for...of` 循环，直到函数的返回值是 `false`。
- 使用 `Array.prototype.slice()` 返回取出的元素。
- 回调函数 `fn` 接受单个参数，即元素的值。

```js
const takeRightWhile = (arr, fn) => {
  for (const [i, val] of [...arr].reverse().entries())
    if (!fn(val)) return i === 0 ? [] : arr.slice(-i);
  return arr;
};
```

```js
takeRightWhile([1, 2, 3, 4], n => n >= 3); // [3, 4]
```
