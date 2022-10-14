---
title: 读取文件行(Read file lines)
tags: node,array
expertise: beginner
cover: blog_images/solitude-beach.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 返回指定文件中的行数组。
> Returns an array of lines from the specified file.

- 使用 `fs.readFileSync()` 从文件创建 `Buffer`。
- 使用 `Buffer.prototype.toString()` 将缓冲区覆盖为字符串。
- 使用 `String.prototype.split()` 从文件的内容创建一个行数组。

```js
const fs = require('fs');

const readFileLines = filename =>
  fs
    .readFileSync(filename)
    .toString('UTF8')
    .split('\n');
```

```js
/*
contents of test.txt :
  line1
  line2
  line3
  ___________________________
*/
let arr = readFileLines('test.txt');
console.log(arr); // ['line1', 'line2', 'line3']
```
