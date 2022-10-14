---
title: 过滤匹配和未指定的值(Filter matching and unspecified values)
tags: array
expertise: intermediate
cover: blog_images/little-bird.jpg
firstSeen: 2017-12-22T09:37:36+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 根据条件过滤对象数组，同时过滤掉未指定的键。
> Filters an array of objects based on a condition while also filtering out unspecified keys.

- 使用 `Array.prototype.filter()` 根据谓词函数 `fn` 过滤数组，使其返回条件返回真值的对象。
- 在过滤后的数组上，使用 `Array.prototype.map()` 返回新对象。
- 使用 `Array.prototype.reduce()` 过滤掉未作为 `keys` 参数提供的键。

```js
const reducedFilter = (data, keys, fn) =>
  data.filter(fn).map(el =>
    keys.reduce((acc, key) => {
      acc[key] = el[key];
      return acc;
    }, {})
  );
```

```js
const data = [
  {
    id: 1,
    name: 'john',
    age: 24
  },
  {
    id: 2,
    name: 'mike',
    age: 50
  }
];
reducedFilter(data, ['id', 'name'], item => item.age > 24);
// [{ id: 2, name: 'mike'}]
```
