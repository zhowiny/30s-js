---
title: 冻结`Set`对象(Freeze Set object)
tags: array
expertise: intermediate
author: maciv
cover: blog_images/frozen-globe.jpg
firstSeen: 2020-10-11T11:52:48+03:00
lastUpdated: 2020-10-11T11:52:48+03:00
---

### 创建一个冻结的 `Set` 对象。
> Creates a frozen `Set` object.

- 使用 `Set` 构造函数从 `iterable` 创建一个新的 `Set` 对象。
- 将新创建对象的 `add`、`delete` 和 `clear` 方法设置为 `undefined`，使用 `Reflect.DeleteProperty()` 删除对象属性，使其无法使用，实际上冻结了对象。

```js
const frozenSet = iterable => {
  const s = new Set(iterable);
  s.add = undefined;
  s.delete = undefined;
  s.clear = undefined;
  Reflect.deleteProperty(s, 'add');
  Reflect.deleteProperty(s, 'delete');
  Reflect.deleteProperty(s, 'clear');
  return s;
};
```

```js
frozenSet([1, 2, 3, 1, 2]);
// Set { 1, 2, 3, add: undefined, delete: undefined, clear: undefined }
```
