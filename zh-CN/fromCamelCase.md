---
title: 驼峰字符串转其他格式(String from camelcase)
tags: string
expertise: intermediate
cover: blog_images/mountain-lake-cottage.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 从驼峰式转换字符串。
> Converts a string from camelcase.

- 使用 `String.prototype.replace()` 将字符串分解为单词并在它们之间添加一个 `separator`。
- 省略第二个参数以使用默认的 `_` 分隔符。

```js
const fromCamelCase = (str, separator = '_') =>
  str
    .replace(/([a-z\d])([A-Z])/g, '$1' + separator + '$2')
    .replace(/([A-Z]+)([A-Z][a-z\d]+)/g, '$1' + separator + '$2')
    .toLowerCase();
```

```js
fromCamelCase('someDatabaseFieldName', ' '); // 'some database field name'
fromCamelCase('someLabelThatNeedsToBeDecamelized', '-');
// 'some-label-that-needs-to-be-decamelized'
fromCamelCase('someJavascriptProperty', '_'); // 'some_javascript_property'
fromCamelCase('JSONToCSV', '.'); // 'json.to.csv'
```
