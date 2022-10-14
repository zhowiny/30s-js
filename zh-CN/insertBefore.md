---
title: 在元素前插入 HTML 字符串(Insert HTML string before element)
tags: browser
expertise: beginner
cover: blog_images/engine.jpg
firstSeen: 2018-06-19T20:57:58+03:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 在指定元素的开始之前插入一个 HTML 字符串。
> Inserts an HTML string before the start of the specified element.

- 使用 `Element.insertAdjacentHTML()` 和 `'beforebegin'` 的位置来解析 `htmlString` 并将其插入到 `el` 的开始之前。

```js
const insertBefore = (el, htmlString) =>
  el.insertAdjacentHTML('beforebegin', htmlString);
```

```js
insertBefore(document.getElementById('myId'), '<p>before</p>');
// <p>before</p> <div id="myId">...</div>
```
