---
title: 反转字符串(Reverse string)
tags: string
expertise: beginner
cover: blog_images/type-stamps.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-18T14:58:09+03:00
---

### 反转一个字符串。
> Reverses a string.

- 使用扩展运算符 (`...`) 和 `Array.prototype.reverse()` 来反转字符串中字符的顺序。
- 使用 `Array.prototype.join()` 组合字符以获取字符串。

```js
const reverseString = str => [...str].reverse().join('');
```

```js
reverseString('foobar'); // 'raboof'
```
