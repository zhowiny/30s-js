---
title: HSL 转数组(HSL to array)
tags: string,browser,regexp
expertise: beginner
cover: blog_images/kettle-laptop.jpg
firstSeen: 2020-10-16T21:46:29+03:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 将 `hsl()` 颜色字符串转换为值数组。
> Converts an `hsl()` color string to an array of values.

- 使用 `String.prototype.match()` 获取一个包含 3 个字符串的数组，其中包含数值。
- 结合使用 `Array.prototype.map()` 和 `Number` 将它们转换为数值数组。

```js
const toHSLArray = hslStr => hslStr.match(/\d+/g).map(Number);
```

```js
toHSLArray('hsl(50, 10%, 10%)'); // [50, 10, 10]
```
