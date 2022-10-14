---
title: 删除空格(Remove whitespaces)
tags: string,regexp
expertise: beginner
cover: blog_images/tropical-bike.jpg
firstSeen: 2020-10-13T09:37:17+03:00
lastUpdated: 2020-11-03T21:46:13+02:00
---

# 返回删除了空格的字符串。
> Returns a string with whitespaces removed.

- 使用带有正则表达式的 `String.prototype.replace()` 将所有出现的空白字符替换为空字符串。

```js
const removeWhitespace = str => str.replace(/\s+/g, '');
```

```js
removeWhitespace('Lorem ipsum.\n Dolor sit amet. ');
// 'Loremipsum.Dolorsitamet.'
```
