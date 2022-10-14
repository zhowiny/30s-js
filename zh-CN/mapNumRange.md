---
title: 将数字映射到范围(Map number to range)
tags: math
expertise: beginner
cover: blog_images/clutter.jpg
firstSeen: 2019-02-23T12:38:16+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

# 将数字从一个范围映射到另一个范围。
> Maps a number from one range to another range.

- 从`inMin`-`inMax`返回`outMin`-`outMax`之间映射的`num`。

```js
const mapNumRange = (num, inMin, inMax, outMin, outMax) =>
  ((num - inMin) * (outMax - outMin)) / (inMax - inMin) + outMin;
```

```js
mapNumRange(5, 0, 10, 0, 100); // 50
```
