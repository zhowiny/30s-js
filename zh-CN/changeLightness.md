---
title: 改变颜色亮度(Change color lightness)
tags: string,browser,regexp
expertise: intermediate
cover: blog_images/aerial-view-port.jpg
firstSeen: 2020-10-30T17:38:31+02:00
lastUpdated: 2020-10-31T16:37:54+02:00
---

# 更改 `hsl()` 颜色字符串的亮度值。
> Changes the lightness value of an `hsl()` color string.

- 使用 `String.prototype.match()` 获得一个包含 3 个字符串的数组，其中包含数值。
- 结合使用 `Array.prototype.map()` 和 `Number` 将它们转换为数值数组。
- 使用 `Math.max()` 和 `Math.min()` 确保亮度在有效范围内（在 `0` 和 `100` 之间）。
- 使用模板文字创建具有更新值的新 `hsl()` 字符串。

```js
const changeLightness = (delta, hslStr) => {
  const [hue, saturation, lightness] = hslStr.match(/\d+/g).map(Number);

  const newLightness = Math.max(
    0,
    Math.min(100, lightness + parseFloat(delta))
  );

  return `hsl(${hue}, ${saturation}%, ${newLightness}%)`;
};
```

```js
changeLightness(10, 'hsl(330, 50%, 50%)'); // 'hsl(330, 50%, 60%)'
changeLightness(-10, 'hsl(330, 50%, 50%)'); // 'hsl(330, 50%, 40%)'
```
