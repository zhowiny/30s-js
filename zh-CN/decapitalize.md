---
title: 取消大写字符串(Decapitalize string)
tags: string
expertise: intermediate
cover: blog_images/forest-balcony.jpg
firstSeen: 2018-01-11T11:58:40+02:00
lastUpdated: 2020-11-01T20:50:57+02:00
---

# 将字符串的第一个字母取消大写。
> Decapitalizes the first letter of a string.

- 使用数组解构和 `String.prototype.toLowerCase()` 对第一个字母进行去大写，`...rest` 在第一个字母之后获取字符数组，然后使用 `Array.prototype.join()` 使其再次成为字符串 .
- 省略 `upperRest` 参数以保持字符串的其余部分不变，或将其设置为 `true` 以转换为大写。

```js
const decapitalize = ([first, ...rest], upperRest = false) =>
  first.toLowerCase() +
  (upperRest ? rest.join('').toUpperCase() : rest.join(''));
```

```js
decapitalize('FooBar'); // 'fooBar'
decapitalize('FooBar', true); // 'fOOBAR'
```
