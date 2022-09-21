---
title: 分组数组元素(Group array elements)
tags: array
expertise: intermediate
cover: blog_images/orange-flower.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

### 创建一个元素数组，根据它们在原始数组中的位置进行分组。
> Creates an array of elements, grouped based on their position in the original arrays.

- 使用 `Math.max()`、`Function.prototype.apply()` 获取参数中最长的数组。
- 创建一个具有该长度作为返回值的数组，并使用 `Array.from()` 和映射函数来创建一个分组元素数组。
- 如果参数数组的长度不同，则在找不到值的地方使用 `undefined`。

```js
const zip = (...arrays) => {
  const maxLength = Math.max(...arrays.map(x => x.length));
  return Array.from({ length: maxLength }).map((_, i) => {
    return Array.from({ length: arrays.length }, (_, k) => arrays[k][i]);
  });
};
```

```js
zip(['a', 'b'], [1, 2], [true, false]); // [['a', 1, true], ['b', 2, false]]
zip(['a'], [1, 2], [true, false]); // [['a', 1, true], [undefined, 2, false]]
```
