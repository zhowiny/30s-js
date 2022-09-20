---
title: 设置元素的样式(Set style for element)
tags: browser
expertise: beginner
cover: blog_images/laptop-plants-2.jpg
firstSeen: 2017-12-29T00:08:17+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 为指定的 HTML 元素设置 CSS 规则的值。
> Sets the value of a CSS rule for the specified HTML element.

- 使用 `HTMLElement.style` 将指定元素的 CSS `rule` 的值设置为 `val`。

```js
const setStyle = (el, rule, val) => (el.style[rule] = val);
```

```js
setStyle(document.querySelector('p'), 'font-size', '20px');
// 第一个 <p> 元素在页面上的字体大小为 20px
```
