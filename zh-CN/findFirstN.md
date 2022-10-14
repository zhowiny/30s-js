---
title: 查找前 n 个匹配项(Find first n matches)
tags: array
expertise: intermediate
cover: blog_images/digital-nomad-5.jpg
firstSeen: 2021-05-09T13:31:36+03:00
lastUpdated: 2021-05-09T13:31:36+03:00
---

# 查找提供的函数为其返回真值的前 `n` 个元素。
> Finds the first `n` elements for which the provided function returns a truthy value.

- 使用 `for...in` 循环为 `arr` 的每个元素执行提供的 `matcher`。
- 使用 `Array.prototype.push()` 将元素附加到结果数组并在其 `length` 等于 `n` 时返回它们。

```js
const findFirstN = (arr, matcher, n = 1) => {
  let res = [];
  for (let i in arr) {
    const el = arr[i];
    const match = matcher(el, i, arr);
    if (match) res.push(el);
    if (res.length === n) return res;
  }
  return res;
};
```

```js
findFirstN([1, 2, 4, 6], n => n % 2 === 0, 2); // [2, 4]
findFirstN([1, 2, 4, 6], n => n % 2 === 0, 5); // [2, 4, 6]
```
