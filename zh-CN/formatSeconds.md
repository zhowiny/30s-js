---
title: ISO 格式的秒数(Number of seconds to ISO format)
tags: date,math,string
expertise: intermediate
cover: blog_images/rocky-mountains.jpg
firstSeen: 2021-05-09T12:44:55+03:00
lastUpdated: 2021-10-13T19:29:39+02:00
---

# 返回给定秒数的 ISO 格式。
> Returns the ISO format of the given number of seconds.

- 将`s`除以适当的值以获得`hour`、`minute`和`second`的适当值。
- 将“符号”存储在变量中以将其添加到结果中。
- 结合使用 `Array.prototype.map()` 和 `Math.floor()` 和 `String.prototype.padStart()` 对每个段进行字符串化和格式化。
- 使用 `Array.prototype.join()` 将值组合成一个字符串。

```js
const formatSeconds = s => {
  const [hour, minute, second, sign] =
    s > 0
      ? [s / 3600, (s / 60) % 60, s % 60, '']
      : [-s / 3600, (-s / 60) % 60, -s % 60, '-'];

  return (
    sign +
    [hour, minute, second]
      .map(v => `${Math.floor(v)}`.padStart(2, '0'))
      .join(':')
  );
};
```

```js
formatSeconds(200); // '00:03:20'
formatSeconds(-200); // '-00:03:20'
formatSeconds(99999); // '27:46:39'
```
