---
title: 投射到数组(Cast to array)
tags: type,array
expertise: beginner
cover: blog_images/man-red-sunset.jpg
firstSeen: 2018-01-23T20:54:12+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 如果它不是一个数组，则将提供的值转换为数组。
> Casts the provided value as an array if it's not one.

- 使用 `Array.prototype.isArray()` 来确定 `val` 是否是一个数组，并将其按原样返回或相应地封装在一个数组中。

```js
const castArray = val => (Array.isArray(val) ? val : [val]);
```

```js
castArray('foo'); // ['foo']
castArray([1]); // [1]
```
