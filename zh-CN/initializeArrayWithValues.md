---
title: 用值初始化数组(Initialize array with values)
tags: array
expertise: intermediate
cover: blog_images/flower-portrait-1.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 用指定的值初始化并填充数组。
> Initializes and fills an array with the specified values.

- 使用 `Array.from()` 创建所需长度的数组，`Array.prototype.fill()` 用所需值填充它。
- 省略最后一个参数 `val`，使用默认值 `0`。

```js
const initializeArrayWithValues = (n, val = 0) =>
  Array.from({ length: n }).fill(val);
```

```js
initializeArrayWithValues(5, 2); // [2, 2, 2, 2, 2]
```
