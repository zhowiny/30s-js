---
title: RGB 转 HSL(RGB to HSL)
tags: math
expertise: intermediate
cover: blog_images/planning.jpg
firstSeen: 2020-10-01T23:16:30+03:00
lastUpdated: 2020-10-04T11:25:12+03:00
---

### 将 RGB 颜色元组转换为 HSL 格式。
> Converts a RGB color tuple to HSL format.

- 使用【RGB 到 HSL 转换公式】(https://www.niwa.nu/2013/05/math-behind-colorspace-conversions-rgb-hsl/) 转换成合适的格式。
- 所有输入参数的范围是[0, 255]。
- 结果值的范围是H：[0, 360]，S：[0, 100]，L：[0, 100]。

```js
const RGBToHSL = (r, g, b) => {
  r /= 255;
  g /= 255;
  b /= 255;
  const l = Math.max(r, g, b);
  const s = l - Math.min(r, g, b);
  const h = s
    ? l === r
      ? (g - b) / s
      : l === g
      ? 2 + (b - r) / s
      : 4 + (r - g) / s
    : 0;
  return [
    60 * h < 0 ? 60 * h + 360 : 60 * h,
    100 * (s ? (l <= 0.5 ? s / (2 * l - s) : s / (2 - (2 * l - s))) : 0),
    (100 * (2 * l - s)) / 2,
  ];
};
```

```js
RGBToHSL(45, 23, 11); // [21.17647, 60.71428, 10.98039]
```
