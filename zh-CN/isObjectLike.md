---
title: 值是类似对象(Value is object-like)
tags: type,object
expertise: beginner
cover: blog_images/orange-flower.jpg
firstSeen: 2018-01-23T19:30:03+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

### 检查一个值是否类似于对象。
> Checks if a value is object-like.

- 检查提供的值是否不是 `null` 并且它的 `typeof` 等于 `'object'`。

```js
const isObjectLike = val => val !== null && typeof val === 'object';
```

```js
isObjectLike({}); // true
isObjectLike([1, 2, 3]); // true
isObjectLike(x => x); // false
isObjectLike(null); // false
```
