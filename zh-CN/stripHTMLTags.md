---
title: 去除 HTML 标签(Strip HTML tags)
tags: string,regexp
expertise: beginner
cover: blog_images/coffee-phone-tray-3.jpg
firstSeen: 2018-01-26T14:17:29+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 从字符串中删除 HTML/XML 标记。
> Removes HTML/XML tags from string.

- 使用正则表达式从字符串中删除 HTML/XML 标记。

```js
const stripHTMLTags = str => str.replace(/<[^>]*>/g, '');
```

```js
stripHTMLTags('<p><em>lorem</em> <strong>ipsum</strong></p>'); // 'lorem ipsum'
```
