---
title: 检查集合的所有元素是否为真(Truth check collection)
tags: object,logic,array
expertise: intermediate
cover: blog_images/digital-nomad-8.jpg
firstSeen: 2017-12-18T13:05:21+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

# 检查谓词函数对于集合的所有元素是否为真。
> Checks if the predicate function is truthy for all elements of a collection.

- 使用 `Array.prototype.every()` 检查每个传递的对象是否具有指定的属性以及是否返回真值。

```js
const truthCheckCollection = (collection, pre) =>
  collection.every(obj => obj[pre]);
```

```js
truthCheckCollection(
  [
    { user: 'Tinky-Winky', sex: 'male' },
    { user: 'Dipsy', sex: 'male' },
  ],
  'sex'
); // true
```
