---
title: JSON 转 CSV(逗号分隔值)(JSON to CSV)
tags: array,string,object
expertise: advanced
cover: blog_images/horse-sunset.jpg
firstSeen: 2018-07-06T20:25:46+03:00
lastUpdated: 2021-10-13T19:29:39+02:00
---

### 将对象数组转换为仅包含指定的 `columns` 的逗号分隔值 (CSV) 字符串。
> Converts an array of objects to a comma-separated values (CSV) string that contains only the `columns` specified.

- 使用 `Array.prototype.join()` 来组合 `columns` 中的所有名称以创建第一行，使用提供的 `delimiter`。
- 使用 `Array.prototype.map()` 和 `Array.prototype.reduce()` 为每个对象创建一行。 用空字符串替换不存在的值，并且仅在“列”中映射值。
- 使用 `Array.prototype.join()` 将所有行组合成一个字符串，用换行符 (`\n`) 分隔每一行。
- 省略第三个参数 `delimiter`，以使用默认分隔符 `','`。

```js
const JSONtoCSV = (arr, columns, delimiter = ',') =>
  [
    columns.join(delimiter),
    ...arr.map(obj =>
      columns.reduce(
        (acc, key) =>
          `${acc}${!acc.length ? '' : delimiter}"${!obj[key] ? '' : obj[key]}"`,
        ''
      )
    ),
  ].join('\n');
```

```js
JSONtoCSV(
  [{ a: 1, b: 2 }, { a: 3, b: 4, c: 5 }, { a: 6 }, { b: 7 }],
  ['a', 'b']
); // 'a,b\n"1","2"\n"3","4"\n"6",""\n"","7"'
JSONtoCSV(
  [{ a: 1, b: 2 }, { a: 3, b: 4, c: 5 }, { a: 6 }, { b: 7 }],
  ['a', 'b'],
  ';'
); // 'a;b\n"1";"2"\n"3";"4"\n"6";""\n"";"7"'
```
