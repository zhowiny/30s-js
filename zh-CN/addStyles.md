---
title: 添加样式到HTML元素(Add styles to HTML element)
tags: browser
expertise: beginner
author: chalarangelo
cover: blog_images/digital-nomad-14.jpg
firstSeen: 2021-01-07T00:37:43+02:00
lastUpdated: 2021-01-07T00:37:43+02:00
---

### 将提供的样式添加到给定的 HTML 元素。
> Adds the provided styles to the given HTML element.

- 使用 `Object.assign()` 和 `ElementCSSInlineStyle.style` 将提供的“styles”对象合并到给定元素的样式中。

```js
const addStyles = (el, styles) => Object.assign(el.style, styles);
```

```js
addStyles(document.getElementById('my-element'), {
  background: 'red',
  color: '#ffff00',
  fontSize: '3rem'
});
```
