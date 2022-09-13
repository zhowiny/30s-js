---
title: 小写对象的key(Lowercase object keys)
tags: object
expertise: intermediate
cover: blog_images/forest-balcony.jpg
firstSeen: 2017-12-29T13:28:18+02:00
lastUpdated: 2020-10-20T11:21:07+03:00
---

### 从指定的对象创建一个新对象，其中所有的键都是小写的。
> Creates a new object from the specified object, where all the keys are in lowercase.

- 使用 `Object.keys()` 和 `Array.prototype.reduce()` 从指定对象创建一个新对象。
- 使用 `String.prototype.toLowerCase()` 将原始对象中的每个键转换为小写。

```js
const lowercaseKeys = obj =>
  Object.keys(obj).reduce((acc, key) => {
    acc[key.toLowerCase()] = obj[key];
    return acc;
  }, {});
```

```js
const myObj = { Name: 'Adam', sUrnAME: 'Smith' };
const myObjLower = lowercaseKeys(myObj); // {name: 'Adam', surname: 'Smith'};
```
