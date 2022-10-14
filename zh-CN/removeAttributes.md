---
title: 删除属性(Remove attributes)
tags: browser
expertise: beginner
cover: blog_images/new-york.jpg
author: chalarangelo
firstSeen: 2022-07-20T05:00:00-04:00
---

# 从 HTML 元素中删除所有属性。
> Removes all attributes from an HTML element.

- 使用 `Element.attributes` 和 `Object.values()` 获取元素的所有属性。
- 使用 `Array.prototype.forEach()` 和对象解构来获取每个属性的名称，并使用 `Element.removeAttribute()` 将其从元素中删除。

```js
const removeAttributes = element =>
  Object.values(element.attributes).forEach(({ name }) =>
    element.removeAttribute(name)
  );
```

```js
removeAttributes(document.querySelector('p.special'));
// 该`p`标签将不再具有'special'属性
```
