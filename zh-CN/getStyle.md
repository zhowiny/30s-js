---
title: 获取元素的样式(Get style for element)
tags: browser,css
expertise: beginner
cover: blog_images/frog-blue-flower.jpg
firstSeen: 2017-12-29T00:08:17+02:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

# 检索指定元素的 CSS 规则的值。
> Retrieves the value of a CSS rule for the specified element.

- 使用 `Window.getComputedStyle()` 获取指定元素的 CSS 规则的值。

```js
const getStyle = (el, ruleName) => getComputedStyle(el)[ruleName];
```

```js
getStyle(document.querySelector('p'), 'font-size'); // '16px'
```
