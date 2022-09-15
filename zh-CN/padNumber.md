---
title: 填充数字(Pad number)
tags: string,math
expertise: beginner
author: maciv
cover: blog_images/flower-portrait-2.jpg
firstSeen: 2020-10-03T23:31:08+03:00
lastUpdated: 2020-10-03T23:31:08+03:00
---

### 将给定数字填充到指定长度。
> Pads a given number to the specified length.

- 使用 `String.prototype.padStart()` 将数字填充到指定长度，然后将其转换为字符串。

```js
const padNumber = (n, l) => `${n}`.padStart(l, '0');
```

```js
padNumber(1234, 6); // '001234'
```
