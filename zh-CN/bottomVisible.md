---
title: 检查是否到了页面底部(Check if bottom of page is visible)
tags: browser
expertise: beginner
cover: blog_images/red-mountain.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 检查页面底部是否可见
> Checks if the bottom of the page is visible.

- 使用 `Window.scrollY`、`Element.scrollHeight` 和 `Element.clientHeight` 来确定页面底部是否可见。

```js
const bottomVisible = () =>
  document.documentElement.clientHeight + window.scrollY >=
  (document.documentElement.scrollHeight ||
    document.documentElement.clientHeight);
```

```js
bottomVisible(); // true
```
