---
title: 切换 HTML 元素的类(Toggle class of HTML element)
tags: browser
expertise: beginner
cover: blog_images/laptop-plants-2.jpg
firstSeen: 2017-12-28T23:46:33+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 切换一个 HTML 元素的类。
> Toggles a class for an HTML element.

- 使用 `Element.classList` 和 `DOMTokenList.toggle()` 来切换元素的指定类。

```js
const toggleClass = (el, className) => el.classList.toggle(className);
```

```js
toggleClass(document.querySelector('p.special'), 'special');
// 该段落将不再具有 'special' 类
```
