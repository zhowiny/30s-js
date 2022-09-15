---
title: 选取对象键(Pick object keys)
tags: object
expertise: intermediate
cover: blog_images/fruit-feast.jpg
firstSeen: 2017-12-13T23:51:34+02:00
lastUpdated: 2020-10-18T14:58:09+03:00
---

### 从对象中选择与给定键对应的键值对。
> Picks the key-value pairs corresponding to the given keys from an object.

- 如果对象中存在键，则使用 `Array.prototype.reduce()` 将过滤/挑选的键转换回具有相应键值对的对象。

```js
const pick = (obj, arr) =>
  arr.reduce((acc, curr) => (curr in obj && (acc[curr] = obj[curr]), acc), {});
```

```js
pick({ a: 1, b: '2', c: 3 }, ['a', 'c']); // { 'a': 1, 'c': 3 }
```
