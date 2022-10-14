---
title: 反转对象(Invert object)
tags: object
expertise: advanced
cover: blog_images/pineapple-on-green.jpg
firstSeen: 2018-01-01T17:33:46+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 反转对象反转对象的键值对，而不改变它。
> Inverts the key-value pairs of an object, without mutating it.

- 使用 `Object.keys()` 和 `Array.prototype.reduce()` 反转对象的键值对并应用提供的函数（如果有）。
- 省略第二个参数，`fn`，以获取反转键而不对其应用函数。
- 每个反转键对应的反转值是一个键数组，负责生成反转值。 如果提供了一个函数，它将应用于每个反转键。

```js
const invertKeyValues = (obj, fn) =>
  Object.keys(obj).reduce((acc, key) => {
    const val = fn ? fn(obj[key]) : obj[key];
    acc[val] = acc[val] || [];
    acc[val].push(key);
    return acc;
  }, {});
```

```js
invertKeyValues({ a: 1, b: 2, c: 1 }); // { 1: [ 'a', 'c' ], 2: [ 'b' ] }
invertKeyValues({ a: 1, b: 2, c: 1 }, value => 'group' + value);
// { group1: [ 'a', 'c' ], group2: [ 'b' ] }
```
