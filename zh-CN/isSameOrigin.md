---
title: 同源 URL(Same-origin URLs)
tags: object
expertise: beginner
author: chalarangelo
cover: blog_images/keyboard-tea.jpg
firstSeen: 2021-04-22T08:27:41+03:00
lastUpdated: 2021-04-22T08:27:41+03:00
---

# 检查两个 URL 是否在同一个来源。
> Checks if two URLs are on the same origin.

- 使用 `URL.protocol` 和 `URL.host` 检查两个 URL 是否具有相同的协议和主机。

```js
const isSameOrigin = (origin, destination) =>
  origin.protocol === destination.protocol && origin.host === destination.host;
```

```js
const origin = new URL('https://www.30secondsofcode.org/about');
const destination = new URL('https://www.30secondsofcode.org/contact');
isSameOrigin(origin, destination); // true
const other = new URL('https://developer.mozilla.org);
isSameOrigin(origin, other); // false
```
