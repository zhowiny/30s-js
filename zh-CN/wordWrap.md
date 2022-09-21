---
title: 自动换行字符串(Word wrap string)
tags: string,regexp
expertise: intermediate
cover: blog_images/white-tablet.jpg
firstSeen: 2020-10-06T11:48:41+03:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

### 使用字符串分隔符将字符串包装成给定数量的字符。
> Wraps a string to a given number of characters using a string break character.

- 使用 `String.prototype.replace()` 和正则表达式在 `max` 字符的最近空白处插入给定的中断字符。
- 省略第三个参数 `br`，以使用默认值 `'\n'`。

```js
const wordWrap = (str, max, br = '\n') => str.replace(
  new RegExp(`(?![^\\n]{1,${max}}$)([^\\n]{1,${max}})\\s`, 'g'), '$1' + br
);
```

```js
wordWrap(
  'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce tempus.',
  32
);
// 'Lorem ipsum dolor sit amet,\nconsectetur adipiscing elit.\nFusce tempus.'
wordWrap(
  'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce tempus.',
  32,
  '\r\n'
);
// 'Lorem ipsum dolor sit amet,\r\nconsectetur adipiscing elit.\r\nFusce tempus.'
```
