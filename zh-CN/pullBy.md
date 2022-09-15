---
title: 根据函数从数组中拉取值(Pull values from array based on function)
tags: array
expertise: advanced
cover: blog_images/fishermen.jpg
firstSeen: 2018-01-26T13:48:50+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

### 根据给定的迭代器函数改变原始数组以过滤掉指定的值。
> Mutates the original array to filter out the values specified, based on a given iterator function.

- 检查提供的最后一个参数是否是一个函数。
- 使用 `Array.prototype.map()` 将迭代器函数 `fn` 应用于所有数组元素。
- 使用 `Array.prototype.filter()` 和 `Array.prototype.includes()` 拉出不需要的值。
- 设置 `Array.prototype.length` 以通过将数组长度重置为 `0` 来改变传入的数组。
- 使用 `Array.prototype.push()` 仅使用拉取的值重新填充它。

```js
const pullBy = (arr, ...args) => {
  const length = args.length;
  let fn = length > 1 ? args[length - 1] : undefined;
  fn = typeof fn == 'function' ? (args.pop(), fn) : undefined;
  let argState = (Array.isArray(args[0]) ? args[0] : args).map(val => fn(val));
  let pulled = arr.filter((v, i) => !argState.includes(fn(v)));
  arr.length = 0;
  pulled.forEach(v => arr.push(v));
};
```

```js
var myArray = [{ x: 1 }, { x: 2 }, { x: 3 }, { x: 1 }];
pullBy(myArray, [{ x: 1 }, { x: 3 }], o => o.x); // myArray = [{ x: 2 }]
```
