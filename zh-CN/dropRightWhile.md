---
title: 根据函数从右侧删除数组元素(Drop list elements from the right based on function)
tags: array
expertise: intermediate
cover: blog_images/bridge-drop.jpg
firstSeen: 2018-01-26T12:23:18+02:00
lastUpdated: 2020-10-19T18:51:03+03:00
---

### 从数组末尾删除元素，直到传递的函数返回 `true`。
返回数组中剩余的元素。
> Removes elements from the end of an array until the passed function returns `true`.
> Returns the remaining elements in the array.

- 遍历数组，使用 `Array.prototype.slice()` 删除数组的最后一个元素，直到 `func` 返回的值为 `true`。
- 返回剩余的元素。

```js
const dropRightWhile = (arr, func) => {
  let rightIndex = arr.length;
  while (rightIndex-- && !func(arr[rightIndex]));
  return arr.slice(0, rightIndex + 1);
};
```

```js
dropRightWhile([1, 2, 3, 4], n => n < 3); // [1, 2]
```
