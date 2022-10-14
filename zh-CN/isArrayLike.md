---
title: 值是类数组(Value is array-like)
tags: type,array
expertise: intermediate
cover: blog_images/colorful-plastic.jpg
firstSeen: 2017-12-31T14:53:01+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 检查提供的参数是否类似于数组（即可迭代）。
> Checks if the provided argument is array-like (i.e. is iterable).

- 检查提供的参数是否不是 `null` 并且它的 `Symbol.iterator` 属性是一个函数。

```js
const isArrayLike = obj =>
  obj != null && typeof obj[Symbol.iterator] === 'function';
```

```js
isArrayLike([1, 2, 3]); // true
isArrayLike(document.querySelectorAll('.className')); // true
isArrayLike('abc'); // true
isArrayLike(null); // false
```
