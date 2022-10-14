---
title: 烤串式字符串(Kebabcase string)
tags: string,regexp
expertise: intermediate
cover: blog_images/old-consoles.jpg
firstSeen: 2017-12-22T19:14:51+02:00
lastUpdated: 2020-12-16T13:42:27+02:00
---

# 将字符串转换为烤串式字符串。
> Converts a string to kebab case.

- 使用 `String.prototype.match()` 使用适当的正则表达式将字符串分解为单词。
- 使用 `Array.prototype.map()`、`Array.prototype.join()` 和 `String.prototype.toLowerCase()` 组合它们，添加 `-` 作为分隔符。

```js
const toKebabCase = str =>
  str &&
  str
    .match(/[A-Z]{2,}(?=[A-Z][a-z]+[0-9]*|\b)|[A-Z]?[a-z]+[0-9]*|[A-Z]|[0-9]+/g)
    .map(x => x.toLowerCase())
    .join('-');
```

```js
toKebabCase('camelCase'); // 'camel-case'
toKebabCase('some text'); // 'some-text'
toKebabCase('some-mixed_string With spaces_underscores-and-hyphens');
// 'some-mixed-string-with-spaces-underscores-and-hyphens'
toKebabCase('AllThe-small Things'); // 'all-the-small-things'
toKebabCase('IAmEditingSomeXMLAndHTML');
// 'i-am-editing-some-xml-and-html'
```
