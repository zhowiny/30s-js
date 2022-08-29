---
title: 组合对象数组(Combine object arrays)
tags: array,object
expertise: intermediate
author: chalarangelo
cover: blog_images/digital-nomad-6.jpg
firstSeen: 2020-10-04T00:26:51+03:00
lastUpdated: 2020-10-08T02:22:39+03:00
---

### 组合两个对象数组，使用指定的键来匹配对象。
> Combines two arrays of objects, using the specified key to match objects.

- 使用 `Array.prototype.reduce()` 和对象累加器，根据给定的 `prop` 组合两个数组中的所有对象。
- 使用 `Object.values()` 将结果对象转换为数组并返回。

```js
const combine = (a, b, prop) =>
  Object.values(
    [...a, ...b].reduce((acc, v) => {
      if (v[prop])
        acc[v[prop]] = acc[v[prop]]
          ? { ...acc[v[prop]], ...v }
          : { ...v };
      return acc;
    }, {})
  );
```

```js
const x = [
  { id: 1, name: 'John' },
  { id: 2, name: 'Maria' }
];
const y = [
  { id: 1, age: 28 },
  { id: 3, age: 26 },
  { age: 3}
];
combine(x, y, 'id');
// [
//  { id: 1, name: 'John', age: 28 },
//  { id: 2, name: 'Maria' },
//  { id: 3, age: 26 }
// ]
```
