---
title: 元素包含另一个元素(Element contains another element)
tags: browser
expertise: intermediate
cover: blog_images/red-petals.jpg
firstSeen: 2018-06-19T20:57:58+03:00
lastUpdated: 2020-11-03T22:11:18+02:00
---

# 检查 `parent` 元素是否包含 `child` 元素。
> Checks if the `parent` element contains the `child` element.

- 检查 `parent` 是否与 `child` 不是同一个元素。
- 使用 `Node.contains()` 检查 `parent` 元素是否包含 `child` 元素。

```js
const elementContains = (parent, child) =>
  parent !== child && parent.contains(child);
```

```js
elementContains(
  document.querySelector('head'),
  document.querySelector('title')
);
// true
elementContains(document.querySelector('body'), document.querySelector('body'));
// false
```
