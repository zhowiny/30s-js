---
title: 摄氏度转换为华氏度(Celsius to Fahrenheit)
tags: math
expertise: beginner
unlisted: true
cover: blog_images/last-light.jpg
firstSeen: 2020-04-16T11:00:06+03:00
lastUpdated: 2021-01-04T13:04:15+02:00
---

# 将摄氏度转换为华氏度。
> Converts Celsius to Fahrenheit.

- 遵循转换公式 `F = 1.8 * C + 32` 。

```js
const celsiusToFahrenheit = degrees => 1.8 * degrees + 32;
```

```js
celsiusToFahrenheit(33); // 91.4
```
