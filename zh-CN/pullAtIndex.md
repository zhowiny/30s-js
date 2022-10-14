---
title: 从索引处的数组中拉取值(Pull values from array at index)
tags: array
expertise: advanced
cover: blog_images/bug.jpg
firstSeen: 2017-12-19T00:42:47+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 对原始数组进行变异以过滤掉指定索引处的值。返回移除的元素。
> Mutates the original array to filter out the values at the specified indexes.
> Returns the removed elements.

- 使用 `Array.prototype.filter()` 和 `Array.prototype.includes()` 拉出不需要的值。
- 设置 `Array.prototype.length` 以通过将数组长度重置为 `0` 来改变传入的数组。
- 使用 `Array.prototype.push()` 仅使用拉取的值重新填充它。
- 使用 `Array.prototype.push()` 来跟踪拉取的值。

```js
const pullAtIndex = (arr, pullArr) => {
  let removed = [];
  let pulled = arr
    .map((v, i) => (pullArr.includes(i) ? removed.push(v) : v))
    .filter((v, i) => !pullArr.includes(i));
  arr.length = 0;
  pulled.forEach(v => arr.push(v));
  return removed;
};
```

```js
let myArray = ['a', 'b', 'c', 'd'];
let pulled = pullAtIndex(myArray, [1, 3]);
// myArray = [ 'a', 'c' ] , pulled = [ 'b', 'd' ]
```
