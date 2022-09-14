---
title: 根据函数匹配对象属性(Matches object properties based on function)
tags: object
expertise: intermediate
cover: blog_images/watermelon-bike.jpg
firstSeen: 2018-01-23T20:17:32+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 根据提供的函数，比较两个对象以确定第一个对象是否包含与第二个对象等效的属性值。
> Compares two objects to determine if the first one contains equivalent property values to the second one, based on a provided function.

- 使用 `Object.keys()` 获取第二个对象的所有键。
- 使用 `Array.prototype.every()`、`Object.prototype.hasOwnProperty()` 和提供的函数来确定第一个对象中是否存在所有键并具有等效值。
- 如果未提供函数，则将使用相等运算符比较值。

```js
const matchesWith = (obj, source, fn) =>
  Object.keys(source).every(key =>
    obj.hasOwnProperty(key) && fn
      ? fn(obj[key], source[key], key, obj, source)
      : obj[key] == source[key]
  );
```

```js
const isGreeting = val => /^h(?:i|ello)$/.test(val);
matchesWith(
  { greeting: 'hello' },
  { greeting: 'hi' },
  (oV, sV) => isGreeting(oV) && isGreeting(sV)
); // true
```
