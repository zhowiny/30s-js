---
title: 华氏到摄氏(Fahrenheit to Celsius)
tags: math
expertise: beginner
unlisted: true
cover: blog_images/last-light.jpg
firstSeen: 2020-04-16T11:00:06+03:00
lastUpdated: 2021-01-04T13:04:15+02:00
---

# 将华氏温度转换为摄氏温度。
> Converts Fahrenheit to Celsius.

- 遵循转换公式 `C = (F - 32) * 5 / 9`。

```js
const fahrenheitToCelsius = degrees => (degrees - 32) * 5 / 9;
```

```js
fahrenheitToCelsius(32); // 0
```
