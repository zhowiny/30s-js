---
title: 添加class到HTML元素(Add class to HTML element)
tags: browser
expertise: beginner
author: chalarangelo
cover: blog_images/budapest-palace.jpg
firstSeen: 2020-12-30T19:21:15+02:00
lastUpdated: 2020-12-30T19:21:15+02:00
---

# 添加class到HTML元素
> Adds a class to an HTML element.

- 使用 `Element.classList` and `DOMTokenList.add()` 将指定的class添加到元素。

```js
const addClass = (el, className) => el.classList.add(className);
```

```js
addClass(document.querySelector('p'), 'special');
// 该p元素现在将具有 “special” class名
```
