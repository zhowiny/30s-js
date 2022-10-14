---
title: CSV(逗号分隔值)转数组(CSV to array)
tags: string,array
expertise: intermediate
cover: blog_images/keyboard-tea.jpg
firstSeen: 2018-06-27T20:57:54+03:00
lastUpdated: 2022-01-30T12:14:39+02:00
---

# 将逗号分隔值 (CSV) 字符串转换为二维数组。
> Converts a comma-separated values (CSV) string to a 2D array.

- 使用 `Array.prototype.indexOf()` 查找第一个换行符（`\n`）。
- 如果 `omitFirstRow` 为 `true`，则使用 `Array.prototype.slice()` 删除第一行（标题行）。
- 使用 `String.prototype.split()` 为每一行创建一个字符串。
- 使用 `String.prototype.split()` 分隔每行中的值，使用提供的 `delimiter`。
- 省略第二个参数 `delimiter`，以使用默认分隔符 `','`。
- 省略第三个参数 `omitFirstRow`，以包含 CSV 字符串的第一行（标题行）。

```js
const CSVToArray = (data, delimiter = ',', omitFirstRow = false) =>
  data
    .slice(omitFirstRow ? data.indexOf('\n') + 1 : 0)
    .split('\n')
    .map(v => v.split(delimiter));
```

```js
CSVToArray('a,b\nc,d'); // [['a', 'b'], ['c', 'd']];
CSVToArray('a;b\nc;d', ';'); // [['a', 'b'], ['c', 'd']];
CSVToArray('col1,col2\na,b\nc,d', ',', true); // [['a', 'b'], ['c', 'd']];
```
