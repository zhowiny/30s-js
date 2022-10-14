---
title: 选择匹配的对象键(Pick matching object keys)
tags: object
expertise: intermediate
cover: blog_images/lake-bench.jpg
firstSeen: 2018-01-19T13:23:45+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 创建一个由给定函数为其返回真值的属性组成的对象。
> Creates an object composed of the properties the given function returns truthy for.

- 使用 `Object.keys()` 和 `Array.prototype.filter()` 删除 `fn` 返回错误值的键。
- 使用 `Array.prototype.reduce()` 将过滤后的键转换回具有相应键值对的对象。
- 使用两个参数调用回调函数： (value, key)。

```js
const pickBy = (obj, fn) =>
  Object.keys(obj)
    .filter(k => fn(obj[k], k))
    .reduce((acc, key) => ((acc[key] = obj[key]), acc), {});
```

```js
pickBy({ a: 1, b: '2', c: 3 }, x => typeof x === 'number');
// { 'a': 1, 'c': 3 }
```
