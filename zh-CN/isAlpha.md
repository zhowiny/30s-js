---
title: 字符串是否只包含字母(String is alpha)
tags: string,regexp
expertise: beginner
cover: blog_images/coffee-phone-tray-3.jpg
firstSeen: 2020-12-31T14:01:42+02:00
lastUpdated: 2020-12-31T14:01:42+02:00
---

# 检查字符串是否仅包含字母字符。
> Checks if a string contains only alpha characters.

- 使用 `RegExp.prototype.test()` 检查给定的字符串是否与字母正则表达式模式匹配。

```js
const isAlpha = str => /^[a-zA-Z]*$/.test(str);
```

```js
isAlpha('sampleInput'); // true
isAlpha('this Will fail'); // false
isAlpha('123'); // false
```
