---
title: 隐藏元素(Hide elements)
tags: browser,css
expertise: beginner
cover: blog_images/book-chair.jpg
firstSeen: 2017-12-28T23:33:21+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 隐藏所有指定的元素。
> Hides all the elements specified.

- 使用扩展运算符 (`...`) 和 `Array.prototype.forEach()` 将 `display: none` 应用于指定的每个元素。

```js
const hide = (...el) => [...el].forEach(e => (e.style.display = 'none'));
```

```js
hide(...document.querySelectorAll('img')); // 页面上隐藏所有 <img> 元素
```
