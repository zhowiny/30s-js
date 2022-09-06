---
title: 检查对象相等性(Check object equality)
tags: object,array,type,recursion
expertise: advanced
cover: blog_images/beach-pineapple.jpg
firstSeen: 2018-01-15T18:34:11+02:00
lastUpdated: 2021-10-13T19:29:39+02:00
---

### 在两个值之间执行深度比较以确定它们是否相等。
> Performs a deep comparison between two values to determine if they are equivalent.

- 检查两个值是否相同。
- 使用 `Date.prototype.getTime()` 检查两个值是否是具有相同时间的 `Date` 对象。
- 检查两个值是否是具有等效值的非对象值（严格比较）。
- 检查是否只有一个值是 `null` 或 `undefined` 或者它们的原型是否不同。
- 如果以上条件都不满足，请使用 `Object.keys()` 检查两个值是否具有相同数量的键。
- 使用 `Array.prototype.every()` 来检查 `a` 中的每个键是否存在于 `b` 中，以及它们是否通过递归调用 `equals()` 等价。

```js
const equals = (a, b) => {
  if (a === b) return true;

  if (a instanceof Date && b instanceof Date)
    return a.getTime() === b.getTime();

  if (!a || !b || (typeof a !== 'object' && typeof b !== 'object'))
    return a === b;

  if (a.prototype !== b.prototype) return false;

  const keys = Object.keys(a);
  if (keys.length !== Object.keys(b).length) return false;

  return keys.every(k => equals(a[k], b[k]));
};
```

```js
equals(
  { a: [2, { e: 3 }], b: [4], c: 'foo' },
  { a: [2, { e: 3 }], b: [4], c: 'foo' }
); // true
equals([1, 2, 3], { 0: 1, 1: 2, 2: 3 }); // true
```
