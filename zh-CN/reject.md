---
title: 拒绝不匹配的值(Reject non-matching values)
tags: array
expertise: beginner
cover: blog_images/interior-7.jpg
firstSeen: 2018-04-27T03:17:15+03:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

### 根据谓词函数过滤数组的值，只返回谓词函数返回`false`的值。
> Filters an array's values based on a predicate function, returning only values for which the predicate function returns `false`.

- 将 `Array.prototype.filter()` 与谓词函数 `pred` 结合使用，仅返回它返回 `false` 的值。

```js
const reject = (pred, array) => array.filter((...args) => !pred(...args));
```

```js
reject(x => x % 2 === 0, [1, 2, 3, 4, 5]); // [1, 3, 5]
reject(word => word.length > 4, ['Apple', 'Pear', 'Kiwi', 'Banana']);
// ['Pear', 'Kiwi']
```
