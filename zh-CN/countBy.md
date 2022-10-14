---
title: 分组元素计数(Count grouped elements)
tags: array,object
expertise: intermediate
cover: blog_images/tools.jpg
firstSeen: 2018-01-11T13:45:53+02:00
lastUpdated: 2020-11-03T22:11:18+02:00
---

# 根据给定函数对数组的元素进行分组，并返回每组中元素的计数。
> Groups the elements of an array based on the given function and returns the count of elements in each group.

- 使用 `Array.prototype.map()` 将数组的值映射到函数或属性名称。
- 使用 `Array.prototype.reduce()` 创建一个对象，其中的键是从映射的结果中产生的。

```js
const countBy = (arr, fn) =>
  arr.map(typeof fn === 'function' ? fn : val => val[fn]).reduce((acc, val) => {
    acc[val] = (acc[val] || 0) + 1;
    return acc;
  }, {});
```

```js
countBy([6.1, 4.2, 6.3], Math.floor); // {4: 1, 6: 2}
countBy(['one', 'two', 'three'], 'length'); // {3: 2, 5: 1}
countBy([{ count: 5 }, { count: 10 }, { count: 5 }], x => x.count)
// {5: 2, 10: 1}
```
