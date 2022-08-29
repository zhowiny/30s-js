---
title: 紧凑的空格(Compact whitespaces)
tags: string,regexp
expertise: beginner
cover: blog_images/travel-mug-1.jpg
firstSeen: 2018-12-12T19:11:33+02:00
lastUpdated: 2020-10-18T23:04:45+03:00
---

### 压缩字符串中的空格。
> Compacts whitespaces in a string.

- 使用带有正则表达式的 `String.prototype.replace()` 将所有出现的 2 个或更多空白字符替换为单个空格。

```js
const compactWhitespace = str => str.replace(/\s{2,}/g, ' ');
```

```js
compactWhitespace('Lorem    Ipsum'); // 'Lorem Ipsum'
compactWhitespace('Lorem \n Ipsum'); // 'Lorem Ipsum'
```
