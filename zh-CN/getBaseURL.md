---
title: 获取base URL(Get base URL)
tags: string,browser,regexp
expertise: beginner
author: chalarangelo
cover: blog_images/compass.jpg
firstSeen: 2020-05-03T12:20:54+03:00
lastUpdated: 2021-01-03T20:32:13+02:00
---

# 获取不带任何参数或片段标识符的当前 URL。
> Gets the current URL without any parameters or fragment identifiers.

- 使用 `String.prototype.replace()` 和适当的正则表达式来删除 `'?'` 或 `'#'` 之后的所有内容（如果找到）。

```js
const getBaseURL = url => url.replace(/[?#].*$/, '');
```

```js
getBaseURL('http://url.com/page?name=Adam&surname=Smith');
// 'http://url.com/page'
```
