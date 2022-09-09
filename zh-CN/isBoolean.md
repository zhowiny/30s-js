---
title: 值是布尔类型(Value is boolean)
tags: type
expertise: beginner
cover: blog_images/book-stopper.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

### 检查给定参数是否是布尔原始类型。
> Checks if the given argument is a native boolean element.

- 使用 `typeof` 检查一个值是否被归类为布尔原始类型。

```js
const isBoolean = val => typeof val === 'boolean';
```

```js
isBoolean(null); // false
isBoolean(false); // true
```
