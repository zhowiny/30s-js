---
title: 可迭代对象转对象(Iterable to hash)
tags: array
expertise: intermediate
cover: blog_images/sleepy-cat.jpg
firstSeen: 2018-05-31T02:14:04+03:00
lastUpdated: 2022-01-30T12:45:30+03:00
---

### 将给定的迭代转为为对象（key存储数据）。
> Reduces a given iterable into a value hash (keyed data store).

- 使用`Object.values()`获取可迭代对象（对象或数组）的值。
- 使用 `Array.prototype.reduce()` 对值进行迭代并创建一个对象，以引用值为 `key`。

```js
const toHash = (object, key) =>
  Object.values(object).reduce((acc, data, index) => {
    acc[!key ? index : data[key]] = data;
    return acc;
  }, {});
```

```js
toHash([4, 3, 2, 1]); // { 0: 4, 1: 3, 2: 2, 3: 1 }
toHash([{ a: 'label' }], 'a'); // { label: { a: 'label' } }
```
