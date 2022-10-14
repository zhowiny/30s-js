---
title: 将数组分成两个(Partition array in two)
tags: array,object
expertise: intermediate
cover: blog_images/sunflowers.jpg
firstSeen: 2018-01-08T16:58:23+02:00
lastUpdated: 2020-11-03T21:46:13+02:00
---

# 根据提供的函数对每个元素的真实性，将元素分组为两个数组。
> Groups the elements into two arrays, depending on the provided function's truthiness for each element.

- 使用 `Array.prototype.reduce()` 创建一个包含两个数组的数组。
- 使用`Array.prototype.push()`将`fn`返回`true`的元素添加到第一个数组，`fn`返回`false`的元素添加到第二个数组。

```js
const partition = (arr, fn) =>
  arr.reduce(
    (acc, val, i, arr) => {
      acc[fn(val, i, arr) ? 0 : 1].push(val);
      return acc;
    },
    [[], []]
  );
```

```js
const users = [
  { user: 'barney', age: 36, active: false },
  { user: 'fred', age: 40, active: true },
];
partition(users, o => o.active);
// [
//   [{ user: 'fred', age: 40, active: true }],
//   [{ user: 'barney', age: 36, active: false }]
// ]
```
