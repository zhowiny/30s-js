---
title: 找到最近的锚点(Find closest anchor)
tags: browser
expertise: intermediate
author: chalarangelo
cover: blog_images/colorful-lounge.jpg
firstSeen: 2021-04-22T08:45:39+03:00
lastUpdated: 2021-04-22T08:45:39+03:00
---

### 查找最接近给定 `node` 的锚节点（如果有）。
> Finds the anchor node closest to the given `node`, if any.

- 使用 `for` 循环和 `Node.parentNode` 从给定的 `node` 向上遍历节点树。
- 使用 `Node.nodeName` 和 `String.prototype.toLowerCase()` 检查任何给定节点是否是锚点（`'a'`）。
- 如果没有找到匹配的节点，则返回 `null`。

```js
const findClosestAnchor = node => {
  for (let n = node; n.parentNode; n = n.parentNode)
    if (n.nodeName.toLowerCase() === 'a') return n;
  return null;
};
```

```js
findClosestAnchor(document.querySelector('a > span')); // a
```
