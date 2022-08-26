---
title: 数组到 HTML 列表(Array to HTML list)
tags: browser,array
expertise: intermediate
cover: blog_images/red-succulent.jpg
firstSeen: 2020-10-08T00:02:45+03:00
lastUpdated: 2020-10-20T11:46:23+03:00
---

### 将给定的数组元素转换为 `<li>` 标记并将它们附加到给定 id 的列表中。
> Converts the given array elements into `<li>` tags and appends them to the list of the given id.

- 使用 `Array.prototype.map()` 和 `Document.querySelector()` 创建一个 html 标签列表。

```js
const arrayToHTMLList = (arr, listID) =>
  document.querySelector(`#${listID}`).innerHTML += arr
    .map(item => `<li>${item}</li>`)
    .join('');
```

```js
arrayToHTMLList(['item 1', 'item 2'], 'myListID');
```
