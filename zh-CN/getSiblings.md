---
title: 获取元素的兄弟元素数组(Array of element's siblings)
tags: browser
expertise: intermediate
author: chalarangelo
cover: blog_images/little-white-flowers.jpg
firstSeen: 2020-08-07T15:31:48+03:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

# 返回一个包含给定元素的所有兄弟元素的数组。
> Returns an array containing all the siblings of the given element.

- 使用 `Node.parentNode` 和 `Node.childNodes` 来获取包含在元素父级中的所有元素的 `NodeList`。
- 使用扩展运算符 (`...`) 和 `Array.prototype.filter()` 转换为数组并从中删除给定的元素。

```js
const getSiblings = el =>
  [...el.parentNode.childNodes].filter(node => node !== el);
```

```js
getSiblings(document.querySelector('head')); // ['body']
```
