---
title: 求夹值(Clamp number)
tags: math
expertise: beginner
cover: blog_images/clay-pot-horizon.jpg
firstSeen: 2017-12-20T19:19:18+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 将 num 限制在边界值 a 和 b 指定的包含范围内。
> Clamps `num` within the inclusive range specified by the boundary values `a` and `b`.

- 如果`num`在范围内，返回`num`。
- 否则，返回范围内最接近的数字。

```js
const clampNumber = (num, a, b) =>
  Math.max(Math.min(num, Math.max(a, b)), Math.min(a, b));
```

```js
clampNumber(2, 3, 5); // 3
clampNumber(1, -1, -5); // -1
```
