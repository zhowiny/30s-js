---
title: 将制表符展开为空格(Expand tabs into spaces)
tags: string,regexp
expertise: beginner
author: chalarangelo
cover: blog_images/houses-rock-sea.jpg
firstSeen: 2020-06-01T17:05:39+03:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 将制表符转换为空格，其中每个制表符对应 `count` 个空格。
> Convert tabs to spaces, where each tab corresponds to `count` spaces.

- 使用带有正则表达式的 `String.prototype.replace()` 和 `String.prototype.repeat()` 将每个制表符替换为 `count` 空格。

```js
const expandTabs = (str, count) => str.replace(/\t/g, ' '.repeat(count));
```

```js
expandTabs('\t\tlorem', 3); // '      lorem'
```
