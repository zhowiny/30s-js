---
title: 检查对象是否有`key``(Check if object has key)
tags: object
expertise: intermediate
author: chalarangelo
cover: blog_images/cloudy-mountaintop.jpg
firstSeen: 2019-10-15T15:45:13+03:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 检查目标值是否存在于 JSON 对象中。
> Checks if the target value exists in a JSON object.

- 检查 `keys` 是否为非空，并使用 `Array.prototype.every()` 依次检查对象内部深度 `obj` 的键。
- 使用 `Object.prototype.hasOwnProperty()` 检查 `obj` 是否没有当前键或不是对象，停止传播并返回 `false`。
- 否则将键的值分配给 `obj` 以在下一次迭代中使用。
- 如果给定的键列表为空，则预先返回 `false`。

```js
const hasKey = (obj, keys) => {
  return (
    keys.length > 0 &&
    keys.every(key => {
      if (typeof obj !== 'object' || !obj.hasOwnProperty(key)) return false;
      obj = obj[key];
      return true;
    })
  );
};
```

```js
let obj = {
  a: 1,
  b: { c: 4 },
  'b.d': 5
};
hasKey(obj, ['a']); // true
hasKey(obj, ['b']); // true
hasKey(obj, ['b', 'c']); // true
hasKey(obj, ['b.d']); // true
hasKey(obj, ['d']); // false
hasKey(obj, ['c']); // false
hasKey(obj, ['b', 'f']); // false
```
