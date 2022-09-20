---
title: 蛇式字符串(Snakecase string)
tags: string,regexp
expertise: intermediate
cover: blog_images/rustic-cup.jpg
firstSeen: 2017-12-22T18:13:22+02:00
lastUpdated: 2021-06-28T15:27:44+03:00
---

### 将字符串转换为蛇式字符串。
> Converts a string to snake case.

- 使用 `String.prototype.match()` 使用适当的正则表达式将字符串分解为单词。
- 使用 `Array.prototype.map()`、`Array.prototype.slice()`、`Array.prototype.join()` 和 `String.prototype.toLowerCase()` 组合它们，添加 `_` 作为一个分隔符。

```js
const toSnakeCase = str =>
  str &&
  str
    .match(/[A-Z]{2,}(?=[A-Z][a-z]+[0-9]*|\b)|[A-Z]?[a-z]+[0-9]*|[A-Z]|[0-9]+/g)
    .map(x => x.toLowerCase())
    .join('_');
```

```js
toSnakeCase('camelCase'); // 'camel_case'
toSnakeCase('some text'); // 'some_text'
toSnakeCase('some-mixed_string With spaces_underscores-and-hyphens');
// 'some_mixed_string_with_spaces_underscores_and_hyphens'
toSnakeCase('AllThe-small Things'); // 'all_the_small_things'
toSnakeCase('IAmEditingSomeXMLAndHTML');
// 'i_am_editing_some_xml_and_html'
```
