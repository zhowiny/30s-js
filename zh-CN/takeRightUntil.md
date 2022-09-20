---
title: 从末尾取出数组元素，直到满足条件(Remove list elements from the end until condition is met)
tags: array
expertise: intermediate
cover: blog_images/fruit-feast.jpg
firstSeen: 2020-11-29T12:04:53+02:00
lastUpdated: 2020-11-29T12:04:53+02:00
---

### 从数组末尾取出元素，直到传递的函数返回 `true`。返回取出的元素。
> Removes elements from the end of an array until the passed function returns `true`.
> Returns the removed elements.

- 使用展开运算符 (`...`) 和 `Array.prototype.reverse()` 创建数组的反向副本。
- 遍历反向副本，使用 `Array.prototype.entries()` 上的 `for...of` 循环，直到函数返回的值是真实的。
- 使用 `Array.prototype.slice()` 返回取出的元素。
- 回调函数 `fn` 接受单个参数，即元素的值。

```js
const takeRightUntil = (arr, fn) => {
  for (const [i, val] of [...arr].reverse().entries())
    if (fn(val)) return i === 0 ? [] : arr.slice(-i);
  return arr;
};
```

```js
takeRightUntil([1, 2, 3, 4], n => n < 3); // [3, 4]
```
