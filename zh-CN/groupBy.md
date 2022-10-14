---
title: 将数组元素分组(Group array elements)
tags: array,object
expertise: intermediate
cover: blog_images/man-cup-laptop.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 根据给定的函数对数组的元素进行分组。
> Groups the elements of an array based on the given function.

- 使用 `Array.prototype.map()` 将数组的值映射到函数或属性名称。
- 使用 `Array.prototype.reduce()` 创建一个对象，其中的键是从映射的结果中产生的。
- **注:** [`Array.prototype.group()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/group)

```js
const groupBy = (arr, fn) =>
  arr
    .map(typeof fn === 'function' ? fn : val => val[fn])
    .reduce((acc, val, i) => {
      acc[val] = (acc[val] || []).concat(arr[i]);
      return acc;
    }, {});
```

```js
groupBy([6.1, 4.2, 6.3], Math.floor); // {4: [4.2], 6: [6.1, 6.3]}
groupBy(['one', 'two', 'three'], 'length'); // {3: ['one', 'two'], 5: ['three']}
```
