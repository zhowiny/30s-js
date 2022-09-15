---
title: 打印带单位的字节数(Pretty-print number of bytes)
tags: string,math
expertise: advanced
cover: blog_images/digital-nomad.jpg
firstSeen: 2018-01-01T18:20:09+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

### 将字节数转换为人类可读的字符串。
> Converts a number in bytes to a human-readable string.

- 使用要根据指数访问的单位的数组字典。
- 使用 `Number.prototype.toPrecision()` 将数字截断为特定位数。
- 通过构建返回美化字符串，考虑提供的选项以及它是否为负。
- 省略第二个参数 `precision`，以使用 `3` 位的默认精度。
- 省略第三个参数 `addSpace`，默认在数字和单位之间添加空格。

```js
const prettyBytes = (num, precision = 3, addSpace = true) => {
  const UNITS = ['B', 'KB', 'MB', 'GB', 'TB', 'PB', 'EB', 'ZB', 'YB'];
  if (Math.abs(num) < 1) return num + (addSpace ? ' ' : '') + UNITS[0];
  const exponent = Math.min(
    Math.floor(Math.log10(num < 0 ? -num : num) / 3),
    UNITS.length - 1
  );
  const n = Number(
    ((num < 0 ? -num : num) / 1000 ** exponent).toPrecision(precision)
  );
  return (num < 0 ? '-' : '') + n + (addSpace ? ' ' : '') + UNITS[exponent];
};
```

```js
prettyBytes(1000); // '1 KB'
prettyBytes(-27145424323.5821, 5); // '-27.145 GB'
prettyBytes(123456789, 3, false); // '123MB'
```
