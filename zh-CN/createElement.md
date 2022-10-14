---
title: 创建 HTML 元素(Create HTML element)
tags: browser
expertise: beginner
cover: blog_images/flower-portrait-4.jpg
firstSeen: 2018-01-05T18:21:44+02:00
lastUpdated: 2020-10-19T18:51:03+03:00
---

# 从字符串创建一个元素（不将其附加到 `document` 中）。
如果给定的字符串包含多个元素，则只返回第一个。
> Creates an element from a string (without appending it to the document).
> If the given string contains multiple elements, only the first one will be returned.

- 使用 `Document.createElement()` 创建一个新元素。
- 使用 `Element.innerHTML` 将其内部 HTML 设置为作为参数提供的字符串。
- 使用 `Element.firstElementChild` 返回字符串的元素版本。

```js
const createElement = str => {
  const el = document.createElement('div');
  el.innerHTML = str;
  return el.firstElementChild;
};
```

```js
const el = createElement(
  `<div class="container">
    <p>Hello!</p>
  </div>`
);
console.log(el.className); // 'container'
```
