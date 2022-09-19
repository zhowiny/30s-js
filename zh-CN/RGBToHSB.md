---
title: RGB 转 HSB(RGB to HSB)
tags: math
expertise: intermediate
cover: blog_images/dark-leaves.jpg
firstSeen: 2020-09-18T14:25:07+03:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 将 RGB 颜色元组转换为 HSB 格式。
> Converts a RGB color tuple to HSB format.

- 使用 [RGB 到 HSB 转换公式](https://en.wikipedia.org/wiki/HSL_and_HSV#From_RGB) 转换为适当的格式。
- 所有输入参数的范围是[0, 255]。
- 结果值的范围是H: [0, 360], S: [0, 100], B: [0, 100]。

```js
const RGBToHSB = (r, g, b) => {
  r /= 255;
  g /= 255;
  b /= 255;
  const v = Math.max(r, g, b),
    n = v - Math.min(r, g, b);
  const h =
    n === 0 ? 0 : n && v === r ? (g - b) / n : v === g ? 2 + (b - r) / n : 4 + (r - g) / n;
  return [60 * (h < 0 ? h + 6 : h), v && (n / v) * 100, v * 100];
};
```

```js
RGBToHSB(252, 111, 48);
// [18.529411764705856, 80.95238095238095, 98.82352941176471]
```
