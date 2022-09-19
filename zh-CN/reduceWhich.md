---
title: 根据提供的函数返回数组的最小值和最大值(Min and max of array based on provided function)
tags: array
expertise: intermediate
cover: blog_images/orange-coffee.jpg
firstSeen: 2018-01-24T12:41:03+02:00
lastUpdated: 2020-11-03T22:11:18+02:00
---

### 在应用提供的函数设置比较规则后，返回数组的最小值/最大值。
> Returns the minimum/maximum value of an array, after applying the provided function to set the comparing rule.

- 结合使用 `Array.prototype.reduce()` 和 `comarator` 函数来获取数组中的适当元素。
- 省略第二个参数 `comparator`，以使用返回数组中最小元素的默认参数。

```js
const reduceWhich = (arr, comparator = (a, b) => a - b) =>
  arr.reduce((a, b) => (comparator(a, b) >= 0 ? b : a));
```

```js
reduceWhich([1, 3, 2]); // 1
reduceWhich([1, 3, 2], (a, b) => b - a); // 3
reduceWhich(
  [
    { name: 'Tom', age: 12 },
    { name: 'Jack', age: 18 },
    { name: 'Lucy', age: 9 }
  ],
  (a, b) => a.age - b.age
); // {name: 'Lucy', age: 9}
```
