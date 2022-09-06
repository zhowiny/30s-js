---
title: 元素被聚焦(Element is focused)
tags: browser
expertise: beginner
author: chalarangelo
cover: blog_images/ice.jpg
firstSeen: 2020-08-07T15:21:27+03:00
lastUpdated: 2020-10-19T18:51:03+03:00
---

### 检查给定元素是否聚焦。
> Checks if the given element is focused.

- 使用 `Document.activeElement` 来确定给定元素是否被聚焦。

```js
const elementIsFocused = el => (el === document.activeElement);
```

```js
elementIsFocused(el); // 如果元素聚焦,则返回 `true`
```
