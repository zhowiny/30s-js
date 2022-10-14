---
title: 首字母大写(Capitalize string)
tags: string
expertise: intermediate
cover: blog_images/digital-nomad-3.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-11-01T20:50:57+02:00
---

# 将字符串的第一个字母大写。
> Capitalizes the first letter of a string.

- 使用数组解构和 `String.prototype.toUpperCase()` 将字符串的第一个字母大写。
- 使用 `Array.prototype.join()` 将大写的 `first` 与字符的 `...rest` 组合起来。
- 省略 `lowerRest` 参数以保持字符串的其余部分不变，或将其设置为 `true` 以转换为小写。

```js
const capitalize = ([first, ...rest], lowerRest = false) =>
  first.toUpperCase() +
  (lowerRest ? rest.join('').toLowerCase() : rest.join(''));
```

```js
capitalize('fooBar'); // 'FooBar'
capitalize('fooBar', true); // 'Foobar'
```
