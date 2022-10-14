---
title: JSON 转文件(JSON to file)
tags: node
expertise: intermediate
cover: blog_images/travel-mug-3.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 将 JSON 对象写入文件。
> Writes a JSON object to a file.

- 使用 `fs.writeFileSync()`、模板文字和 `JSON.stringify()` 将 `json` 对象写入 `.json` 文件。

```js
const fs = require('fs');

const JSONToFile = (obj, filename) =>
  fs.writeFileSync(`${filename}.json`, JSON.stringify(obj, null, 2));
```

```js
JSONToFile({ test: 'is passed' }, 'testJsonFile');
// 将对象写入 'testJsonFile.json'
```
