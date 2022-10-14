---
title: 从数组中拉取值(Pull values from array)
tags: array
expertise: intermediate
cover: blog_images/last-light.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 改变原始数组以过滤掉指定的值。
> Mutates the original array to filter out the values specified.

- 使用 `Array.prototype.filter()` 和 `Array.prototype.includes()` 拉出不需要的值。
- 设置 `Array.prototype.length` 以通过将数组长度重置为 `0` 来改变传入的数组。
- 使用 `Array.prototype.push()` 仅使用拉取的值重新填充它。

```js
const pull = (arr, ...args) => {
  let argState = Array.isArray(args[0]) ? args[0] : args;
  let pulled = arr.filter(v => !argState.includes(v));
  arr.length = 0;
  pulled.forEach(v => arr.push(v));
};
```

```js
let myArray = ['a', 'b', 'c', 'a', 'b', 'c'];
pull(myArray, 'a', 'c'); // myArray = [ 'b', 'b' ]
```
