---
title: 深度冻结对象(Deep freeze object)
tags: object,recursion
expertise: intermediate
cover: blog_images/frozen-globe.jpg
firstSeen: 2018-08-25T18:54:16+03:00
lastUpdated: 2020-10-19T18:51:03+03:00
---

### 深度冻结对象
> Deep freezes an object.

- 使用 `Object.keys()` 获取传递对象的所有属性，`Array.prototype.forEach()` 对它们进行迭代。
- 在所有属性上递归调用 `Object.freeze()`，必要时应用 `deepFreeze()`。
- 最后，使用 `Object.freeze()` 冻结给定的对象。

```js
const deepFreeze = obj => {
  Object.keys(obj).forEach(prop => {
    if (typeof obj[prop] === 'object') deepFreeze(obj[prop]);
  });
  return Object.freeze(obj);
};
```

```js
'use strict';

const val = deepFreeze([1, [2, 3]]);

val[0] = 3; // not allowed
val[1][0] = 4; // not allowed as well
```
