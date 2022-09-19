---
title: 从 HTML 元素中删除class(Remove class from HTML element)
tags: browser
expertise: beginner
author: chalarangelo
cover: blog_images/bag-waiting.jpg
firstSeen: 2020-12-30T19:21:15+02:00
lastUpdated: 2020-12-30T19:21:15+02:00
---

### 从 HTML 元素中移除一个类。
> Removes a class from an HTML element.

- 使用 `Element.classList` 和 `DOMTokenList.remove()` 从元素中删除指定的类。

```js
const removeClass = (el, className) => el.classList.remove(className);
```

```js
removeClass(document.querySelector('p.special'), 'special');
// 该`p`标签将不再具有'special'类
```
