---
title: 在元素后插入 HTML 字符串(Insert HTML string after element)
tags: browser
expertise: beginner
cover: blog_images/malibu.jpg
firstSeen: 2018-06-19T20:57:58+03:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 在指定元素的末尾插入一个 HTML 字符串。
> Inserts an HTML string after the end of the specified element.

- 使用 `Element.insertAdjacentHTML()` 和 `'afterend'` 的位置来解析 `htmlString` 并将其插入到 `el` 的末尾。

```js
const insertAfter = (el, htmlString) =>
  el.insertAdjacentHTML('afterend', htmlString);
```

```js
insertAfter(document.getElementById('myId'), '<p>after</p>');
// <div id="myId">...</div> <p>after</p>
```
