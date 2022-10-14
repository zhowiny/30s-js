---
title: 数组到 CSV(Array to CSV)
tags: array,string
expertise: intermediate
cover: blog_images/sunrise-over-city.jpg
firstSeen: 2018-06-27T20:26:43+03:00
lastUpdated: 2020-11-03T21:55:08+02:00
---

# 将二维数组转换为逗号分隔值 (CSV) 字符串。
> Converts a 2D array to a comma-separated values (CSV) string.

- 使用 `Array.prototype.map()` 和 `Array.prototype.join()` 将单个 一维数组（行）组合成字符串，使用提供的 `delimiter`。
- 使用 `Array.prototype.join()` 将所有行组合成一个 CSV 字符串，用换行符 (`\n`) 分隔每一行。
- 省略第二个参数 `delimiter`，以使用默认分隔符 `,`。

```js
const arrayToCSV = (arr, delimiter = ',') =>
  arr
    .map(v =>
      v.map(x => (isNaN(x) ? `"${x.replace(/"/g, '""')}"` : x)).join(delimiter)
    )
    .join('\n');
```

```js
arrayToCSV([['a', 'b'], ['c', 'd']]); // '"a","b"\n"c","d"'
arrayToCSV([['a', 'b'], ['c', 'd']], ';'); // '"a";"b"\n"c";"d"'
arrayToCSV([['a', '"b" great'], ['c', 3.1415]]);
// '"a","""b"" great"\n"c",3.1415'
```
