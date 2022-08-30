---
title: 如果不存在则创建目录(Create directory if not exists)
tags: node
expertise: beginner
cover: blog_images/sunrise-over-city.jpg
firstSeen: 2018-12-12T19:25:16+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 如果目录不存在，则创建目录。
> Creates a directory, if it does not exist.

- 使用`fs.existsSync()`检查目录是否存在，`fs.mkdirSync()`创建它。

```js
const fs = require('fs');

const createDirIfNotExists = dir =>
  !fs.existsSync(dir) ? fs.mkdirSync(dir) : undefined;
```

```js
createDirIfNotExists('test');
// 创建目录'test'，如果它不存在
```
