---
title: 取出数组元素直到满足条件(Remove list elements until condition is met)
tags: array
expertise: intermediate
cover: blog_images/purple-sunset-beach.jpg
firstSeen: 2020-11-29T12:04:53+02:00
lastUpdated: 2020-11-29T12:04:53+02:00
---

### 取出数组中的元素，直到传递的函数返回 `true`。返回取出的元素。
> Removes elements in an array until the passed function returns `true`.
> Returns the removed elements.

- 遍历数组，使用 `Array.prototype.entries()` 上的 `for...of` 循环，直到函数返回的值是 `true`。
- 使用 `Array.prototype.slice()` 返回取出的元素。
- 回调函数 `fn` 接受单个参数，即元素的值。

```js
const takeUntil = (arr, fn) => {
  for (const [i, val] of arr.entries()) if (fn(val)) return arr.slice(0, i);
  return arr;
};
```

```js
takeUntil([1, 2, 3, 4], n => n >= 3); // [1, 2]
```
