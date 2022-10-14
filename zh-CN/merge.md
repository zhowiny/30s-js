---
title: 合并对象(Merge objects)
tags: object,array
expertise: intermediate
cover: blog_images/guitar-living-room.jpg
firstSeen: 2018-01-12T14:44:20+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

# 从两个或多个对象的组合中创建一个新对象。
> Creates a new object from the combination of two or more objects.

- 使用 `Array.prototype.reduce()` 结合 `Object.keys()` 来迭代所有对象和键。
- 使用 `Object.prototype.hasOwnProperty()` 和 `Array.prototype.concat()` 为多个对象中存在的键附加值。

```js
const merge = (...objs) =>
  [...objs].reduce(
    (acc, obj) =>
      Object.keys(obj).reduce((a, k) => {
        acc[k] = acc.hasOwnProperty(k)
          ? [].concat(acc[k]).concat(obj[k])
          : obj[k];
        return acc;
      }, {}),
    {}
  );
```

```js
const object = {
  a: [{ x: 2 }, { y: 4 }],
  b: 1
};
const other = {
  a: { z: 3 },
  b: [2, 3],
  c: 'foo'
};
merge(object, other);
// { a: [ { x: 2 }, { y: 4 }, { z: 3 } ], b: [ 1, 2, 3 ], c: 'foo' }
```
