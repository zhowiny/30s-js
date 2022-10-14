---
title: 查找最后一个匹配的key(Find last matching key)
tags: object
expertise: intermediate
cover: blog_images/sparkles.jpg
firstSeen: 2018-01-23T18:23:20+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 查找满足提供的测试功能的最后一个键。否则返回 `undefined`。
> Finds the last key that satisfies the provided testing function.
> Otherwise `undefined` is returned.

- 使用 `Object.keys()` 获取对象的所有属性。
- 使用 `Array.prototype.reverse()` 来反转顺序和 `Array.prototype.find()` 来测试每个键值对提供的函数。
- 回调接收三个参数 - 值、键和对象。

```js
const findLastKey = (obj, fn) =>
  Object.keys(obj)
    .reverse()
    .find(key => fn(obj[key], key, obj));
```

```js
findLastKey(
  {
    barney: { age: 36, active: true },
    fred: { age: 40, active: false },
    pebbles: { age: 1, active: true }
  },
  x => x['active']
); // 'pebbles'
```
