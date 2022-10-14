---
title: 元素的垂直偏移(Vertical offset of element)
tags: browser
expertise: beginner
author: chalarangelo
cover: blog_images/waves-from-above-2.jpg
firstSeen: 2021-01-05T22:41:09+02:00
lastUpdated: 2021-01-05T22:41:09+02:00
---

# 查找从给定元素到文档顶部的距离。
> Finds the distance from a given element to the top of the document.

- 使用 `while` 循环和 `HTMLElement.offsetParent` 向上移动给定元素的偏移父项。
- 为每个元素添加 `HTMLElement.offsetTop` 并返回结果。

```js
const getVerticalOffset = el => {
  let offset = el.offsetTop,
    _el = el;
  while (_el.offsetParent) {
    _el = _el.offsetParent;
    offset += _el.offsetTop;
  }
  return offset;
};
```

```js
getVerticalOffset('.my-element'); // 120
```
