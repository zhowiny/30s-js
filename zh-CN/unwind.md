---
title: 展开对象中的数组(Unwind object)
tags: object
expertise: intermediate
author: chalarangelo
cover: blog_images/waves-from-above.jpg
firstSeen: 2022-04-18T05:00:00-04:00
---

# 从对象及其数组值属性之一生成对象数组。
> Produces an array of objects from an object and one of its array-valued properties.

- 使用对象解构从对象中排除指定 `key` 的键值对。
- 使用 `Array.prototype.map()` 为给定 `key` 的值创建对象数组。
- 每个对象都包含原始对象的值，除了映射到其各个值的 `key`。

```js
const unwind = (key, obj) => {
  const { [key]: _, ...rest } = obj;
  return obj[key].map(val => ({ ...rest, [key]: val }));
};
```

```js
unwind('b', { a: true, b: [1, 2] }); // [{ a: true, b: 1 }, { a: true, b: 2 }]
```
