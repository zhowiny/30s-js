---
title: 随机十六进制颜色代码(Random hex color code)
tags: math,random
expertise: beginner
cover: blog_images/feathers.jpg
firstSeen: 2017-12-24T14:39:21+02:00
lastUpdated: 2021-01-08T00:23:44+02:00
---

# 生成随机的十六进制颜色代码。
> Generates a random hexadecimal color code.

- 使用 `Math.random()` 生成随机的 24 位（6 * 4 位）十六进制数。
- 使用位移，然后使用 `Number.prototype.toString()` 将其转换为十六进制字符串。

```js
const randomHexColorCode = () => {
  let n = (Math.random() * 0xfffff * 1000000).toString(16);
  return '#' + n.slice(0, 6);
};
```

```js
randomHexColorCode(); // '#e34155'
```
