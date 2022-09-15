---
title: 从对象数组中提取值(Pluck values from array of objects)
tags: array,object
expertise: beginner
cover: blog_images/birds.jpg
firstSeen: 2020-10-18T01:19:37+03:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

### 将对象数组转换为与指定的`key`对应的值数组。
> Converts an array of objects into an array of values corresponding to the specified `key`.

- 使用 `Array.prototype.map()` 将对象数组映射到每个对象的 `key` 值。

```js
const pluck = (arr, key) => arr.map(i => i[key]);
```

```js
const simpsons = [
  { name: 'lisa', age: 8 },
  { name: 'homer', age: 36 },
  { name: 'marge', age: 34 },
  { name: 'bart', age: 10 }
];
pluck(simpsons, 'age'); // [8, 36, 34, 10]
```
