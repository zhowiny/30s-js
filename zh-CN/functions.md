---
title: 函数属性名称(Function property names)
tags: object,function
expertise: advanced
cover: blog_images/palm-tree-house.jpg
firstSeen: 2018-01-11T21:18:58+02:00
lastUpdated: 2020-10-20T11:21:07+03:00
---

### 从对象自己的（和可选继承的）可枚举属性中获取函数属性名称数组。
> Gets an array of function property names from own (and optionally inherited) enumerable properties of an object.

- 使用 `Object.keys()` 来迭代对象自己的属性。
- 如果 `inherited` 为 `true`，使用 `Object.getPrototypeOf()` 来获取对象的继承属性。
- 使用 `Array.prototype.filter()` 仅保留那些类型为函数的属性。
- 省略第二个参数，`inherited`，默认不包括继承的属性。

```js
const functions = (obj, inherited = false) =>
  (inherited
    ? [...Object.keys(obj), ...Object.keys(Object.getPrototypeOf(obj))]
    : Object.keys(obj)
  ).filter(key => typeof obj[key] === 'function');
```

```js
function Foo() {
  this.a = () => 1;
  this.b = () => 2;
}
Foo.prototype.c = () => 3;
functions(new Foo()); // ['a', 'b']
functions(new Foo(), true); // ['a', 'b', 'c']
```
