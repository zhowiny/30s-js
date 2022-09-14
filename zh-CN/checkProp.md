---
title: 检查属性(Check property)
tags: function,object
expertise: intermediate
cover: blog_images/white-tablet-2.jpg
firstSeen: 2019-03-17T03:53:00+02:00
lastUpdated: 2020-11-01T20:50:57+02:00
---

### 创建一个函数，该函数将为给定对象的指定属性调用谓词函数。
> Creates a function that will invoke a predicate function for the specified property on a given object.

- 返回一个柯里化函数，它将为 `obj` 上的指定 `prop` 调用 `predicate` 并返回一个布尔值。

```js
const checkProp = (predicate, prop) => obj => !!predicate(obj[prop]);
```

```js
const lengthIs4 = checkProp(l => l === 4, 'length');
lengthIs4([]); // false
lengthIs4([1, 2, 3, 4]); // true
lengthIs4(new Set([1, 2, 3, 4])); // false (Set uses Size, not length)

const session = { user: {} };
const validUserSession = checkProp(u => u.active && !u.disabled, 'user');

validUserSession(session); // false

session.user.active = true;
validUserSession(session); // true

const noLength = checkProp(l => l === undefined, 'length');
noLength([]); // false
noLength({}); // true
noLength(new Set()); // true
```
