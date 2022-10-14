---
title: 转义 HTML(Escape HTML)
tags: string,browser,regexp
expertise: intermediate
cover: blog_images/periscope.jpg
firstSeen: 2017-12-29T15:09:21+02:00
lastUpdated: 2021-10-13T19:29:39+02:00
---

# 转义字符串以在 HTML 中使用。
> Escapes a string for use in HTML.

- 将 `String.prototype.replace()` 与匹配需要转义的字符的正则表达式一起使用。
- 使用回调函数使用字典对象将每个字符实例替换为其关联的转义字符。

```js
const escapeHTML = str =>
  str.replace(
    /[&<>'"]/g,
    tag =>
      ({
        '&': '&amp;',
        '<': '&lt;',
        '>': '&gt;',
        "'": '&#39;',
        '"': '&quot;'
      }[tag] || tag)
  );
```

```js
escapeHTML('<a href="#">Me & you</a>');
// '&lt;a href=&quot;#&quot;&gt;Me &amp; you&lt;/a&gt;'
```
