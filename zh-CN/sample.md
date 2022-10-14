---
title: 数组中的随机元素(Random element in array)
tags: array,string,random
expertise: beginner
cover: blog_images/paper-card.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 从数组中获取随机元素。
> Gets a random element from an array.

- 使用 `Math.random()` 生成随机数。
- 将其乘以 `Array.prototype.length` 并使用 `Math.floor()` 将其四舍五入到最接近的整数。
- 此方法也适用于字符串。

```js
const sample = arr => arr[Math.floor(Math.random() * arr.length)];
```

```js
sample([3, 7, 9, 11]); // 9
```
