---
title: HSL 转对象(HSL to object)
tags: string,browser,regexp
expertise: intermediate
cover: blog_images/measuring.jpg
firstSeen: 2020-10-16T21:48:31+03:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 将 `hsl()` 颜色字符串转换为具有每种颜色值的对象。
> Converts an `hsl()` color string to an object with the values of each color.

- 使用 `String.prototype.match()` 获取一个包含 3 个字符串的数组，其中包含数值。
- 结合使用 `Array.prototype.map()` 和 `Number` 将它们转换为数值数组。
- 使用数组解构将值存储到命名变量中，并从中创建适当的对象。

```js
const toHSLObject = hslStr => {
  const [hue, saturation, lightness] = hslStr.match(/\d+/g).map(Number);
  return { hue, saturation, lightness };
};
```

```js
toHSLObject('hsl(50, 10%, 10%)'); // { hue: 50, saturation: 10, lightness: 10 }
```
