---
title: 从数组中拉取匹配值(Pull matching values from array)
tags: array
expertise: advanced
cover: blog_images/light-leaves.jpg
firstSeen: 2017-12-19T08:06:29+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 改变原始数组以过滤掉指定的值。返回移除的元素。
> Mutates the original array to filter out the values specified.
> Returns the removed elements.

- 使用 `Array.prototype.filter()` 和 `Array.prototype.includes()` 拉出不需要的值。
- 设置 `Array.prototype.length` 以通过将数组长度重置为 `0` 来改变传入的数组。
- 使用 `Array.prototype.push()` 仅使用拉取的值重新填充它。
- 使用 `Array.prototype.push()` 来跟踪拉取的值。

```js
const pullAtValue = (arr, pullArr) => {
  let removed = [],
    pushToRemove = arr.forEach((v, i) =>
      pullArr.includes(v) ? removed.push(v) : v
    ),
    mutateTo = arr.filter((v, i) => !pullArr.includes(v));
  arr.length = 0;
  mutateTo.forEach(v => arr.push(v));
  return removed;
};
```

```js
let myArray = ['a', 'b', 'c', 'd'];
let pulled = pullAtValue(myArray, ['b', 'd']);
// myArray = [ 'a', 'c' ] , pulled = [ 'b', 'd' ]
```
