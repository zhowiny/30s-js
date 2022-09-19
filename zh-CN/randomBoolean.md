---
title: 随机布尔值(Random boolean value)
tags: math,random
expertise: beginner
author: chalarangelo
cover: blog_images/malibu.jpg
firstSeen: 2021-01-20T16:20:08+02:00
lastUpdated: 2021-01-20T16:20:08+02:00
---

### 生成一个随机布尔值。
> Generates a random boolean value.

- 使用 `Math.random()` 生成一个随机数并检查它是否大于或等于 `0.5`。

```js
const randomBoolean = () => Math.random() >= 0.5;
```

```js
randomBoolean(); // true
```
