---
title: 查找第一个匹配的 key(Find first matching key)
tags: object
expertise: intermediate
cover: blog_images/succulent-crowd.jpg
firstSeen: 2018-01-23T18:23:20+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 找到满足提供的测试功能的第一个键。否则返回 `undefined`。
> Finds the first key that satisfies the provided testing function.
> Otherwise `undefined` is returned.

- 使用 `Object.keys()` 获取对象的所有属性，`Array.prototype.find()` 使用 `fn` 测试每个键值对。
- 回调接收三个参数 - 值、键和对象。

```js
const findKey = (obj, fn) =>
  Object.keys(obj).find(key => fn(obj[key], key, obj));
```

```js
findKey(
  {
    barney: { age: 36, active: true },
    fred: { age: 40, active: false },
    pebbles: { age: 1, active: true }
  },
  x => x['active']
); // 'barney'
```
