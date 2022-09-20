---
title: RGB 转对象(RGB to object)
tags: string,browser,regexp
expertise: intermediate
author: chalarangelo
cover: blog_images/organizer.jpg
firstSeen: 2020-10-14T21:58:14+03:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

### 将 `rgb()` 颜色字符串转换为具有每种颜色值的对象。
> Converts an `rgb()` color string to an object with the values of each color.

- 使用 `String.prototype.match()` 获取一个包含 3 个字符串的数组，其中包含数值。
- 结合使用 `Array.prototype.map()` 和 `Number` 将它们转换为数值数组。
- 使用数组解构将值存储到命名变量中，并从中创建适当的对象。

```js
const toRGBObject = rgbStr => {
  const [red, green, blue] = rgbStr.match(/\d+/g).map(Number);
  return { red, green, blue };
};
```

```js
toRGBObject('rgb(255, 12, 0)'); // {red: 255, green: 12, blue: 0}
```
