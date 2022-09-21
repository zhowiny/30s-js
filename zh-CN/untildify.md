---
title: 转换为绝对路径(Convert to absolute path)
tags: node,string
expertise: beginner
cover: blog_images/lighthouse.jpg
firstSeen: 2018-01-01T17:43:18+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

### 将波浪号路径转换为绝对路径。
> Converts a tilde path to an absolute path.

- 使用带有正则表达式的 `String.prototype.replace()` 和 `os.homedir()` 将路径开头的 `~` 替换为主目录。

```js
const untildify = str =>
  str.replace(/^~($|\/|\\)/, `${require('os').homedir()}$1`);
```

```js
untildify('~/node'); // '/Users/aUser/node'
```
