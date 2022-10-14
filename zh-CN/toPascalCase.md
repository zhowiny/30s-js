---
title: 帕斯卡大小写字符串(Pascalcase string)
tags: string,regexp
expertise: intermediate
cover: blog_images/camera-zoom.jpg
firstSeen: 2021-09-08T19:21:13+00:00
---

# 将字符串转换为帕斯卡大小写。
> Converts a string to pascal case.

- 使用 `String.prototype.match()` 使用适当的正则表达式将字符串分解为单词。
- 使用 `Array.prototype.map()`、`Array.prototype.slice()`、`Array.prototype.join()`、`String.prototype.toUpperCase()` 和 `String.prototype.toLowerCase() ` 将它们组合起来，每个单词的第一个字母大写，其余的小写。

```js
const toPascalCase = str =>
  str
    .match(/[A-Z]{2,}(?=[A-Z][a-z]+[0-9]*|\b)|[A-Z]?[a-z]+[0-9]*|[A-Z]|[0-9]+/g)
    .map(x => x.charAt(0).toUpperCase() + x.slice(1).toLowerCase())
    .join('');
```

```js
toPascalCase('some_database_field_name'); // 'SomeDatabaseFieldName'
toPascalCase('Some label that needs to be pascalized');
// 'SomeLabelThatNeedsToBePascalized'
toPascalCase('some-javascript-property'); // 'SomeJavascriptProperty'
toPascalCase('some-mixed_string with spaces_underscores-and-hyphens');
// 'SomeMixedStringWithSpacesUnderscoresAndHyphens'
```
