---
title: 大写空格式字符串(Titlecase string)
tags: string,regexp
expertise: intermediate
cover: blog_images/plant-candle.jpg
firstSeen: 2018-10-19T04:49:34+03:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

# 将字符串转换为大写空格式字符串。
> Converts a string to title case.

- 使用 `String.prototype.match()` 使用适当的正则表达式将字符串分解为单词。
- 使用 `Array.prototype.map()`、`Array.prototype.slice()`、`Array.prototype.join()` 和 `String.prototype.toUpperCase()` 组合它们，首字母大写每个单词并在它们之间添加一个空格。

```js
const toTitleCase = str =>
  str
    .match(/[A-Z]{2,}(?=[A-Z][a-z]+[0-9]*|\b)|[A-Z]?[a-z]+[0-9]*|[A-Z]|[0-9]+/g)
    .map(x => x.charAt(0).toUpperCase() + x.slice(1))
    .join(' ');
```

```js
toTitleCase('some_database_field_name'); // 'Some Database Field Name'
toTitleCase('Some label that needs to be title-cased');
// 'Some Label That Needs To Be Title Cased'
toTitleCase('some-package-name'); // 'Some Package Name'
toTitleCase('some-mixed_string with spaces_underscores-and-hyphens');
// 'Some Mixed String With Spaces Underscores And Hyphens'
```
