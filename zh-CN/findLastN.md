---
title: 查找最后 n 个匹配项(Find last n matches)
tags: array
expertise: intermediate
cover: blog_images/interior-16.jpg
firstSeen: 2021-05-09T13:31:36+03:00
lastUpdated: 2021-05-09T13:31:36+03:00
---

### 查找提供的函数为其返回 `true` 值的最后 n 个元素。
> Finds the last `n` elements for which the provided function returns a truthy value.

- 使用 `for` 循环为 `arr` 的每个元素执行提供的 `matcher`。
- 使用 `Array.prototype.unshift()` 将元素添加到结果数组并在其 `length` 等于 `n` 时返回它们。

```js
const findLastN = (arr, matcher, n = 1) => {
  let res = [];
  for (let i = arr.length - 1; i >= 0; i--) {
    const el = arr[i];
    const match = matcher(el, i, arr);
    if (match) res.unshift(el);
    if (res.length === n) return res;
  }
  return res;
};
```

```js
findLastN([1, 2, 4, 6], n => n % 2 === 0, 2); // [4, 6]
findLastN([1, 2, 4, 6], n => n % 2 === 0, 5); // [2, 4, 6]
```
