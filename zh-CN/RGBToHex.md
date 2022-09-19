---
title: RGB转十六进制(RGB to hex)
tags: string,math
expertise: intermediate
cover: blog_images/colors-mural.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-11-03T22:11:18+02:00
---

### 将 RGB 的值转换为十六进制颜色代码。
> Converts the values of RGB components to a hexadecimal color code.

- 使用按位左移运算符 (`<<`) 和 `Number.prototype.toString()` 将给定的 RGB 参数转换为十六进制字符串。
- 使用 `String.prototype.padStart()` 获取 6 位十六进制值。

```js
const RGBToHex = (r, g, b) =>
  ((r << 16) + (g << 8) + b).toString(16).padStart(6, '0');
```

```js
RGBToHex(255, 165, 1); // 'ffa501'
```
