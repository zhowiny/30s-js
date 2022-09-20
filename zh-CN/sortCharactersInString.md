---
title: 将字符串排序(Sort characters in string)
tags: string
expertise: beginner
cover: blog_images/purple-flower-field.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 按字母顺序对字符串中的字符进行排序。
> Alphabetically sorts the characters in a string.

- 使用扩展运算符 (`...`)、`Array.prototype.sort()` 和 `String.prototype.localeCompare()` 对 `str` 中的字符进行排序。
- 使用 `Array.prototype.join()` 重新组合。

```js
const sortCharactersInString = str =>
  [...str].sort((a, b) => a.localeCompare(b)).join('');
```

```js
sortCharactersInString('cabbage'); // 'aabbceg'
```
