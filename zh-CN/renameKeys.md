---
title: 重命名对象键(Rename object keys)
tags: object
expertise: intermediate
cover: blog_images/fallen-leaves.jpg
firstSeen: 2018-04-10T20:22:39+03:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 用提供的值替换多个对象键的名称。
> Replaces the names of multiple object keys with the values provided.

- 使用 `Object.keys()` 结合 `Array.prototype.reduce()` 和扩展运算符 (`...`) 来获取对象的键并根据 `keysMap` 重命名它们。

```js
const renameKeys = (keysMap, obj) =>
  Object.keys(obj).reduce(
    (acc, key) => ({
      ...acc,
      ...{ [keysMap[key] || key]: obj[key] }
    }),
    {}
  );
```

```js
const obj = { name: 'Bobo', job: 'Front-End Master', shoeSize: 100 };
renameKeys({ name: 'firstName', job: 'passion' }, obj);
// { firstName: 'Bobo', passion: 'Front-End Master', shoeSize: 100 }
```
