---
title: 获取元素祖先(Get element ancestors)
tags: browser
expertise: beginner
author: chalarangelo
cover: blog_images/interior-8.jpg
firstSeen: 2020-10-15T09:28:34+03:00
lastUpdated: 2021-01-05T22:45:34+02:00
---

### 返回从文档根到给定元素的元素的所有祖先。
> Returns all the ancestors of an element from the document root to the given element.

- 使用 `Node.parentNode` 和 `while` 循环向上移动元素的祖先树。
- 使用 `Array.prototype.unshift()` 将每个新祖先添加到数组的开头。

```js
const getAncestors = el => {
  let ancestors = [];
  while (el) {
    ancestors.unshift(el);
    el = el.parentNode;
  }
  return ancestors;
};
```

```js
getAncestors(document.querySelector('nav'));
// [document, html, body, header, nav]
```
