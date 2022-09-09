---
title: 值是否为流(Value is stream)
tags: node,type
expertise: intermediate
cover: blog_images/mountain-lake-cottage-2.jpg
firstSeen: 2018-10-01T20:12:19+03:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 检查给定参数是否为流。
> Checks if the given argument is a stream.

- 检查值是否不同于 `null`。
- 使用`typeof`检查值是否为`object`类型，`pipe`属性是否为`function`类型。

```js
const isStream = val =>
  val !== null && typeof val === 'object' && typeof val.pipe === 'function';
```

```js
const fs = require('fs');

isStream(fs.createReadStream('test.txt')); // true
```
