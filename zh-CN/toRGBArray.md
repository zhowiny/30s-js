---
title: RGB 转数组(RGB to array)
tags: string,browser,regexp
expertise: beginner
cover: blog_images/greek-coffee.jpg
firstSeen: 2020-10-14T20:36:18+03:00
lastUpdated: 2021-06-13T13:50:25+03:00
---

### 将 `rgb()` 颜色字符串转换为值数组。
> Converts an `rgb()` color string to an array of values.

- 使用 `String.prototype.match()` 获取一个包含 3 个字符串的数组，其中包含数值。
- 结合使用 `Array.prototype.map()` 和 `Number` 将它们转换为数值数组。

```js
const toRGBArray = rgbStr => rgbStr.match(/\d+/g).map(Number);
```

```js
toRGBArray('rgb(255, 12, 0)'); // [255, 12, 0]
```
