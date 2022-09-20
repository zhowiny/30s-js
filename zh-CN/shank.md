---
title: 从数组中删除元素(Remove elements from array)
tags: array
expertise: intermediate
cover: blog_images/avocado-slices.jpg
excerpt: Removes an element from an array without mutating it.
firstSeen: 2018-09-27T01:55:30+03:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 具有与 [`Array.prototype.splice()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice) 相同的功能，但返回一个新的数组而不是改变原始数组。
> Has the same functionality as [`Array.prototype.splice()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice), but returning a new array instead of mutating the original array.

- 在删除现有元素和/或添加新元素后，使用 `Array.prototype.slice()` 和 `Array.prototype.concat()` 获取包含新内容的数组。
- 省略第二个参数，`index`，从 `0` 开始。
- 省略第三个参数 `delCount`，以删除 `0` 元素。
- 省略第四个参数，`elements`，以便不添加任何新元素。

```js
const shank = (arr, index = 0, delCount = 0, ...elements) =>
  arr
    .slice(0, index)
    .concat(elements)
    .concat(arr.slice(index + delCount));
```

```js
const names = ['alpha', 'bravo', 'charlie'];
const namesAndDelta = shank(names, 1, 0, 'delta');
// [ 'alpha', 'delta', 'bravo', 'charlie' ]
const namesNoBravo = shank(names, 1, 1); // [ 'alpha', 'charlie' ]
console.log(names); // ['alpha', 'bravo', 'charlie']
```
