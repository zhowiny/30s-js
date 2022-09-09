---
title: 检查 HTML 元素是否有`class`(Check if HTML element has class)
tags: browser,css
expertise: beginner
cover: blog_images/interior.jpg
firstSeen: 2017-12-28T23:46:33+02:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 检查给定元素是否具有指定的类。
> Checks if the given element has the specified class.

- 使用 `Element.classList` 和 `DOMTokenList.contains()` 检查元素是否具有指定的类。

```js
const hasClass = (el, className) => el.classList.contains(className);
```

```js
hasClass(document.querySelector('p.special'), 'special'); // true
```
