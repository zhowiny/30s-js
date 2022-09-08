---
title: 查找所有匹配的key(Find matching keys)
tags: object
expertise: beginner
cover: blog_images/beach-riders.jpg
firstSeen: 2020-10-25T09:59:13+02:00
lastUpdated: 2020-11-15T14:43:44+02:00
---

### 在提供的对象中查找与给定值匹配的所有键。
> Finds all the keys in the provided object that match the given value.

- 使用 `Object.keys()` 获取对象的所有属性。
- 使用 `Array.prototype.filter()` 测试每个键值对并返回所有等于给定值的键。

```js
const findKeys = (obj, val) =>
  Object.keys(obj).filter(key => obj[key] === val);
```

```js
const ages = {
  Leo: 20,
  Zoey: 21,
  Jane: 20,
};
findKeys(ages, 20); // [ 'Leo', 'Jane' ]
```
