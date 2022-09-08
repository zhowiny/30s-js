---
title: 格式数字(Format number)
tags: string,math
expertise: beginner
cover: blog_images/laptop-plants.jpg
firstSeen: 2020-07-30T11:38:51+03:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 使用本地数字格式顺序格式化数字。
> Formats a number using the local number format order.

- 使用 `Number.prototype.toLocaleString()` 将数字转换为使用本地数字格式分隔符。

```js
const formatNumber = num => num.toLocaleString();
```

```js
formatNumber(123456); // '123,456' in `en-US`
formatNumber(15675436903); // '15.675.436.903' in `de-DE`
```
