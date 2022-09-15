---
title: 填充字符串(Pad string)
tags: string
expertise: beginner
cover: blog_images/blue-lake.jpg
firstSeen: 2018-02-24T11:51:27+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

### 如果字符串短于指定的 `length`，则用指定的字符填充字符串的两侧。
> Pads a string on both sides with the specified character, if it's shorter than the specified `length`.

- 使用 `String.prototype.padStart()` 和 `String.prototype.padEnd()` 填充给定字符串的两侧。
- 省略第三个参数 `char`，以使用空白字符作为默认填充字符。

```js
const pad = (str, length, char = ' ') =>
  str.padStart((str.length + length) / 2, char).padEnd(length, char);
```

```js
pad('cat', 8); // '  cat   '
pad(String(42), 6, '0'); // '004200'
pad('foobar', 3); // 'foobar'
```
