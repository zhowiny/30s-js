---
title: 检查进程参数是否包含标志(Check if process arguments contain flags)
tags: node
expertise: intermediate
cover: blog_images/white-tablet.jpg
firstSeen: 2018-01-01T18:24:43+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 检查当前进程的参数是否包含指定的标志。
> Checks if the current process's arguments contain the specified flags.

- 使用 `Array.prototype.every()` 和 `Array.prototype.includes()` 检查 `process.argv` 是否包含所有指定的标志。
- 使用正则表达式来测试指定的标志是否以 `-` 或 `--` 为前缀，并相应地为其添加前缀。

```js
const hasFlags = (...flags) =>
  flags.every(flag =>
    process.argv.includes(/^-{1,2}/.test(flag) ? flag : '--' + flag)
  );
```

```js
// node myScript.js -s --test --cool=true
hasFlags('-s'); // true
hasFlags('--test', 'cool=true', '-s'); // true
hasFlags('special'); // false
```
