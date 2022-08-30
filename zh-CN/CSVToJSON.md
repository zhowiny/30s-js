---
title: CSV(逗号分隔值)转JSON(CSV to JSON)
tags: string,object
expertise: advanced
cover: blog_images/kettle-laptop.jpg
firstSeen: 2018-06-27T21:14:24+03:00
lastUpdated: 2022-01-30T12:14:39+02:00
---

### 将逗号分隔值 (CSV) 字符串转换为二维对象数组。
字符串的第一行用作标题行。

> Converts a comma-separated values (CSV) string to a 2D array of objects.
> The first row of the string is used as the title row.

- 使用 `Array.prototype.indexOf()` 查找第一个换行符（`\n`）。
- 使用 `Array.prototype.slice()` 删除第一行（标题行）和 `String.prototype.split()` 使用提供的 `delimiter` 将其分隔为值。
- 使用 `String.prototype.split()` 为每一行创建一个字符串。
- 使用 `String.prototype.split()` 分隔每行中的值，使用提供的 `delimiter`。
- 使用 `Array.prototype.reduce()` 为每一行的值创建一个对象，键从标题行解析。
- 省略第二个参数 `delimiter`，以使用默认分隔符 `,`。

```js
const CSVToJSON = (data, delimiter = ',') => {
  const titles = data.slice(0, data.indexOf('\n')).split(delimiter);
  return data
    .slice(data.indexOf('\n') + 1)
    .split('\n')
    .map(v => {
      const values = v.split(delimiter);
      return titles.reduce(
        (obj, title, index) => ((obj[title] = values[index]), obj),
        {}
      );
    });
};
```

```js
CSVToJSON('col1,col2\na,b\nc,d');
// [{'col1': 'a', 'col2': 'b'}, {'col1': 'c', 'col2': 'd'}];
CSVToJSON('col1;col2\na;b\nc;d', ';');
// [{'col1': 'a', 'col2': 'b'}, {'col1': 'c', 'col2': 'd'}];
```
