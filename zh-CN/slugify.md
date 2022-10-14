---
title: 字符串转 slug(String to slug)
tags: string,regexp
expertise: intermediate
cover: blog_images/houses-rock-sea.jpg
firstSeen: 2020-10-04T09:45:43+03:00
lastUpdated: 2020-10-04T10:36:38+03:00
---

# 将字符串转换为 URL 友好的 slug。
> Converts a string to a URL-friendly slug.

- 使用 `String.prototype.toLowerCase()` 和 `String.prototype.trim()` 来规范化字符串。
- 使用 `String.prototype.replace()` 将空格、破折号和下划线替换为 `-` 并删除特殊字符。

```js
const slugify = str =>
  str
    .toLowerCase()
    .trim()
    .replace(/[^\w\s-]/g, '')
    .replace(/[\s_-]+/g, '-')
    .replace(/^-+|-+$/g, '');
```

```js
slugify('Hello World!'); // 'hello-world'
```
