---
title: 根据函数从左侧删除数组元素(Drop list elements from the left based on function)
tags: array
expertise: intermediate
cover: blog_images/colorful-lounge.jpg
firstSeen: 2018-01-26T12:23:18+02:00
lastUpdated: 2020-10-19T18:51:03+03:00
---

# 删除数组中的元素，直到传递的函数返回 `true`。
返回数组中剩余的元素。
> Removes elements in an array until the passed function returns `true`.
> Returns the remaining elements in the array.

- 遍历数组，使用 `Array.prototype.slice()` 删除数组的第一个元素，直到 `func` 返回的值为 `true`。
- 返回剩余的元素。

```js
const dropWhile = (arr, func) => {
  while (arr.length > 0 && !func(arr[0])) arr = arr.slice(1);
  return arr;
};
```

```js
dropWhile([1, 2, 3, 4], n => n >= 3); // [3, 4]
```
