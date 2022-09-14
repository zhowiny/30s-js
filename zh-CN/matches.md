---
title: 匹配对象属性(Match object properties)
tags: object
expertise: intermediate
cover: blog_images/two-flower-vases.jpg
firstSeen: 2018-01-23T20:17:32+02:00
lastUpdated: 2020-11-03T22:11:18+02:00
---

### 比较两个对象以确定第一个对象是否包含与第二个对象等效的属性值。
> Compares two objects to determine if the first one contains equivalent property values to the second one.

- 使用 `Object.keys()` 获取第二个对象的所有键。
- 使用 `Array.prototype.every()`、`Object.prototype.hasOwnProperty()` 和严格比较来确定第一个对象中是否存在所有键并具有相同的值。

```js
const matches = (obj, source) =>
  Object.keys(source).every(
    key => obj.hasOwnProperty(key) && obj[key] === source[key]
  );
```

```js
matches({ age: 25, hair: 'long', beard: true }, { hair: 'long', beard: true });
// true
matches({ hair: 'long', beard: true }, { age: 25, hair: 'long', beard: true });
// false
```
