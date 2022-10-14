---
title: 数组、对象或字符串的大小(Size of array, object or string)
tags: object,array,string
expertise: intermediate
cover: blog_images/digital-nomad-13.jpg
firstSeen: 2017-12-30T16:46:01+02:00
lastUpdated: 2020-10-21T21:17:45+03:00
---

# 获取数组、对象或字符串的大小。
> Gets the size of an array, object or string.

- 获取 `val` 的类型（`array`、`object` 或 `string`）。
- 对数组使用 `Array.prototype.length` 属性。
- 使用 `length` 或 `size` 值（如果可用）或对象的键数。
- 使用从 `val` 创建的 [`Blob` 对象](https://developer.mozilla.org/en-US/docs/Web/API/Blob) 的`size` 作为字符串。
- 使用 `String.prototype.split()` 将字符串拆分为字符数组并返回其长度。

```js

const size = val =>
  Array.isArray(val)
    ? val.length
    : val && typeof val === 'object'
      ? val.size || val.length || Object.keys(val).length
      : typeof val === 'string'
        ? new Blob([val]).size
        : 0;
```

```js
size([1, 2, 3, 4, 5]); // 5
size('size'); // 4
size({ one: 1, two: 2, three: 3 }); // 3
```
