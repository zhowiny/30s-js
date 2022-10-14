---
title: 移除 DOM 元素(Remove DOM element)
tags: browser
expertise: beginner
author: chalarangelo
cover: blog_images/by-the-lighthouse.jpg
firstSeen: 2021-01-07T00:20:34+02:00
lastUpdated: 2021-01-07T00:20:34+02:00
---

# 从 DOM 中移除一个元素。
> Removes an element from the DOM.

- 使用 `Node.parentNode` 获取给定元素的父节点。
- 使用 `Node.removeChild()` 从其父节点中删除给定元素。

```js
const removeElement = el => el.parentNode.removeChild(el);
```

```js
removeElement(document.querySelector('#my-element'));
// 从DOM中移除 #my-element
```
