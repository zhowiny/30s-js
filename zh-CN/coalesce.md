---
title: 空值参数合并(Argument coalescing)
tags: type
expertise: beginner
cover: blog_images/flower-portrait-1.jpg
firstSeen: 2017-12-17T10:08:55+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 返回第一个定义的非空参数。
> Returns the first defined, non-null argument.

- 使用 `Array.prototype.find()` 和 `Array.prototype.includes()` 查找第一个不等于 `undefined` 或 `null` 的值。

```js
const coalesce = (...args) => args.find(v => ![undefined, null].includes(v));
```

```js
coalesce(null, undefined, '', NaN, 'Waldo'); // ''
```
