---
title: 恢复转义的 HTML(Unescape HTML)
tags: string,browser,regexp
expertise: beginner
cover: blog_images/little-tree.jpg
firstSeen: 2017-12-29T15:09:10+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

### 对转义的 HTML 字符进行转义恢复。
> Unescapes escaped HTML characters.

- 将 `String.prototype.replace()` 与匹配需要转义的字符的正则表达式一起使用。
- 使用函数的回调使用字典（对象）将每个转义字符实例替换为其关联的非转义字符。

```js
const unescapeHTML = str =>
  str.replace(
    /&amp;|&lt;|&gt;|&#39;|&quot;/g,
    tag =>
      ({
        '&amp;': '&',
        '&lt;': '<',
        '&gt;': '>',
        '&#39;': "'",
        '&quot;': '"'
      }[tag] || tag)
  );
```

```js
unescapeHTML('&lt;a href=&quot;#&quot;&gt;Me &amp; you&lt;/a&gt;');
// '<a href="#">Me & you</a>'
```
