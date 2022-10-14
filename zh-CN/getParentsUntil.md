---
title: 获取父元素直到元素匹配选择器(Get parents until element matches selector)
tags: browser
expertise: intermediate
author: chalarangelo
cover: blog_images/colorful-plastic.jpg
firstSeen: 2021-01-05T22:47:21+02:00
lastUpdated: 2021-01-06T13:04:18+02:00
---

# 查找元素的所有祖先，直到与指定选择器匹配的元素。
> Finds all the ancestors of an element up until the element matched by the specified selector.

- 使用 `Node.parentNode` 和 `while` 循环向上移动元素的祖先树。
- 使用 `Array.prototype.unshift()` 将每个新祖先添加到数组的开头。
- 使用 `Element.matches()` 检查当前元素是否匹配指定的 `selector`。

```js
const getParentsUntil = (el, selector) => {
  let parents = [],
    _el = el.parentNode;
  while (_el && typeof _el.matches === 'function') {
    parents.unshift(_el);
    if (_el.matches(selector)) return parents;
    else _el = _el.parentNode;
  }
  return [];
};
```

```js
getParentsUntil(document.querySelector('#home-link'), 'header');
// [header, nav, ul, li]
```
