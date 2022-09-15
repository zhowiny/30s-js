---
title: 根据函数省略对象属性(Omit object properties based on function)
tags: object
expertise: intermediate
cover: blog_images/arrow-functions.jpg
firstSeen: 2018-01-19T13:23:45+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 省略与给定函数为其返回假值对象的键对应的键值对。
> Omits the key-value pairs corresponding to the keys of the object for which the given function returns falsy.

- 使用 `Object.keys()` 和 `Array.prototype.filter()` 删除 `fn` 返回真值的键。
- 使用 `Array.prototype.reduce()` 将过滤后的键转换回具有相应键值对的对象。
- 使用两个参数调用回调函数: (value, key)。

```js
const omitBy = (obj, fn) =>
  Object.keys(obj)
    .filter(k => !fn(obj[k], k))
    .reduce((acc, key) => ((acc[key] = obj[key]), acc), {});
```

```js
omitBy({ a: 1, b: '2', c: 3 }, x => typeof x === 'number'); // { b: '2' }
```
