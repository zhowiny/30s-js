---
title: 查找最近的匹配节点(Find closest matching node)
tags: browser
expertise: intermediate
author: chalarangelo
cover: blog_images/flowering-hills.jpg
firstSeen: 2021-04-22T08:45:39+03:00
lastUpdated: 2021-04-22T08:45:39+03:00
---

# 从给定的 `节点` 开始查找最接近的匹配节点。
> Finds the closest matching node starting at the given `node`.

- 使用 `for` 循环和 `Node.parentNode` 从给定的 `node` 向上遍历节点树。
- 使用 `Element.matches()` 检查任何给定的元素节点是否与提供的 `selector` 匹配。
- 如果没有找到匹配的节点，则返回 `null`。

```js
const findClosestMatchingNode = (node, selector) => {
  for (let n = node; n.parentNode; n = n.parentNode)
    if (n.matches && n.matches(selector)) return n;
  return null;
};
```

```js
findClosestMatchingNode(document.querySelector('span'), 'body'); // body
```
