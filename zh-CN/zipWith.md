---
title: 根据函数对数组元素进行分组(Group array elements based on function)
tags: array
expertise: advanced
cover: blog_images/switzerland-night.jpg
firstSeen: 2018-01-20T17:21:34+02:00
lastUpdated: 2020-11-03T21:46:13+02:00
---

# 创建一个元素数组，根据原始数组中的位置进行分组，并使用函数指定应如何组合分组值。
> Creates an array of elements, grouped based on the position in the original arrays and using a function to specify how grouped values should be combined.

- 检查提供的最后一个参数是否是一个函数。
- 使用 `Math.max()` 获取参数中最长的数组。
- 使用 `Array.from()` 创建一个具有适当长度的数组和一个映射函数来创建分组元素的数组。
- 如果参数数组的长度不同，则在找不到值的地方使用 `undefined`。
- 使用每个组的元素调用该函数。

```js
const zipWith = (...array) => {
  const fn =
    typeof array[array.length - 1] === 'function' ? array.pop() : undefined;
  return Array.from({ length: Math.max(...array.map(a => a.length)) }, (_, i) =>
    fn ? fn(...array.map(a => a[i])) : array.map(a => a[i])
  );
};
```

```js
zipWith([1, 2], [10, 20], [100, 200], (a, b, c) => a + b + c); // [111, 222]
zipWith(
  [1, 2, 3],
  [10, 20],
  [100, 200],
  (a, b, c) =>
    (a != null ? a : 'a') + (b != null ? b : 'b') + (c != null ? c : 'c')
); // [111, 222, '3bc']
```
