---
title: 将对象转换为Map(Convert object to Map)
shortTitle: Object to Map
tags: object
expertise: intermediate
author: chalarangelo
cover: blog_images/succulent-2.jpg
firstSeen: 2022-06-16T05:00:00-04:00
---

### 将对象转换为 `Map`。
> Converts an object to a `Map`.

- 使用 `Object.entries()` 将对象转换为键值对数组。
- 使用 `Map` 构造函数将数组转换为 `Map`。

```js
const objectToMap = obj => new Map(Object.entries(obj));
```

```js
objectToMap({a: 1, b: 2}); // Map {'a' => 1, 'b' => 2}
```
