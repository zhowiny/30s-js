---
title: 数组中最长的项(Longest item in array)
tags: array
expertise: intermediate
cover: blog_images/interior-14.jpg
firstSeen: 2018-01-08T21:33:47+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 获取任意数量的可迭代对象或具有 `length` 属性的对象并返回最长的对象。
> Takes any number of iterable objects or objects with a `length` property and returns the longest one.

- 使用 `Array.prototype.reduce()`，比较对象的长度以找到最长的一个。
- 如果多个对象的长度相同，则返回第一个。
- 如果没有提供参数，则返回 `undefined`。

```js
const longestItem = (...vals) =>
  vals.reduce((a, x) => (x.length > a.length ? x : a));
```

```js
longestItem('this', 'is', 'a', 'testcase'); // 'testcase'
longestItem(...['a', 'ab', 'abc']); // 'abc'
longestItem(...['a', 'ab', 'abc'], 'abcd'); // 'abcd'
longestItem([1, 2, 3], [1, 2], [1, 2, 3, 4, 5]); // [1, 2, 3, 4, 5]
longestItem([1, 2, 3], 'foobar'); // 'foobar'
```
