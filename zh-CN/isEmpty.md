---
title: 集合为空(Collection is empty)
tags: type,array,object,string
expertise: beginner
cover: blog_images/book-chair.jpg
firstSeen: 2018-01-23T19:25:17+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 检查 a 值是否为空对象/集合、没有可枚举属性或任何不被视为集合的类型。
> Checks if the a value is an empty object/collection, has no enumerable properties or is any type that is not considered a collection.

- 检查提供的值是否为 `null` 或其 `length` 是否等于 `0`。

```js
const isEmpty = val => val == null || !(Object.keys(val) || val).length;
```

```js
isEmpty([]); // true
isEmpty({}); // true
isEmpty(''); // true
isEmpty([1, 2]); // false
isEmpty({ a: 1, b: 2 }); // false
isEmpty('text'); // false
isEmpty(123); // true - 类型不被视为集合
isEmpty(true); // true - 类型不被视为集合
```
