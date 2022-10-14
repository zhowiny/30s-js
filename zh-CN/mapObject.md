---
title: 将数组映射到对象(Map array to object)
tags: array,object
expertise: intermediate
cover: blog_images/two-lighthouses.jpg
firstSeen: 2017-12-18T12:11:58+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

# 使用函数将数组的值映射到对象。
> Maps the values of an array to an object using a function.

- 使用 `Array.prototype.reduce()` 将 `fn` 应用于 `arr` 中的每个元素，并将结果组合成一个对象。
- 使用 `el` 作为每个属性的键，使用 `fn` 的结果作为值。

```js
const mapObject = (arr, fn) =>
  arr.reduce((acc, el, i) => {
    acc[el] = fn(el, i, arr);
    return acc;
  }, {});
```

```js
mapObject([1, 2, 3], a => a * a); // { 1: 1, 2: 4, 3: 9 }
```
