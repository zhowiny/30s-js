---
title: 对象深拷贝(Deep clone object)
tags: object,recursion
expertise: advanced
cover: blog_images/pagodas.jpg
firstSeen: 2018-01-23T20:48:46+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 创建对象的深层克隆。克隆原始类型、数组和对象，不包括类实例。
> Creates a deep clone of an object.
> Clones primitives, arrays and objects, excluding class instances.

- 使用递归。
- 检查传递的对象是否为 `null`，如果是，则返回 `null`。
- 使用 `Object.assign()` 和一个空对象 (`{}`) 创建原始的浅克隆。
- 使用 `Object.keys()` 和 `Array.prototype.forEach()` 来确定需要深度克隆的键值对。
- 如果对象是 `Array`，则将 `clone` 的 `length` 设置为原始的，并使用 `Array.from()` 创建一个克隆。

```js
const deepClone = obj => {
  if (obj === null) return null;
  let clone = Object.assign({}, obj);
  Object.keys(clone).forEach(
    key =>
      (clone[key] =
        typeof obj[key] === 'object' ? deepClone(obj[key]) : obj[key])
  );
  if (Array.isArray(obj)) {
    clone.length = obj.length;
    return Array.from(clone);
  }
  return clone;
};
```

```js
const a = { foo: 'bar', obj: { a: 1, b: 2 } };
const b = deepClone(a); // a !== b, a.obj !== b.obj
```
