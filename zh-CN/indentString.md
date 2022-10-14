---
title: 缩进字符串(Indent string)
tags: string
expertise: beginner
cover: blog_images/clutter.jpg
firstSeen: 2018-09-24T22:14:27+03:00
lastUpdated: 2020-11-01T20:50:57+02:00
---

# 缩进提供的字符串中的每一行。
> Indents each line in the provided string.

- 使用 `String.prototype.replace()` 和正则表达式在每行的开头添加 `indent` `count` 次指定的字符。
- 省略第三个参数 `indent`，以使用默认缩进字符 `' '`。

```js
const indentString = (str, count, indent = ' ') =>
  str.replace(/^/gm, indent.repeat(count));
```

```js
indentString('Lorem\nIpsum', 2); // '  Lorem\n  Ipsum'
indentString('Lorem\nIpsum', 2, '_'); // '__Lorem\n__Ipsum'
```
