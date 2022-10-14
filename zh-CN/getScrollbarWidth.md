---
title: 滚动条宽度(Scrollbar width)
tags: browser
expertise: beginner
cover: blog_images/violin.jpg
author: chalarangelo
firstSeen: 2022-07-16T05:00:00-04:00
---

# 计算窗口垂直滚动条的宽度。
> Calculates the width of the window's vertical scrollbar.


- 使用 `Window.innerWidth` 获取窗口的内部宽度。
- 使用 `Element.clientWidth` 获取 `Document` 元素的内部宽度。
- 减去两个值得到垂直滚动条的宽度。

```js
const getScrollbarWidth = () =>
  window.innerWidth - document.documentElement.clientWidth;
```

```js
getScrollbarWidth(); // 15
```
