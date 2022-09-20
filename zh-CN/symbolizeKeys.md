---
title: symbol化对象的key(Symbolize object keys)
tags: object
expertise: advanced
author: chalarangelo
cover: blog_images/rocky-lake.jpg
firstSeen: 2021-08-01T05:00:00-04:00
---

### 创建一个新对象，将每个键转换为 `Symbol`。
> Creates a new object, converting each key to a `Symbol`.

- 使用 `Object.keys()` 获取 `obj` 的键。
- 使用 `Array.prototype.reduce()` 和 `Symbol` 创建一个新对象，其中每个键都转换为 `Symbol`。

```js
const symbolizeKeys = obj =>
  Object.keys(obj).reduce(
    (acc, key) => ({ ...acc, [Symbol(key)]: obj[key] }),
    {}
  );
```

```js
symbolizeKeys({ id: 10, name: 'apple' });
// { [Symbol(id)]: 10, [Symbol(name)]: 'apple' }
```
