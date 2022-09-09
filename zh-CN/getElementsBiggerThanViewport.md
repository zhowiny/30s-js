---
title: 获取大于视口的元素(Get elements bigger than viewport)
tags: browser
expertise: intermediate
cover: blog_images/case-study.jpg
firstSeen: 2020-10-06T17:41:22+03:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 返回宽度大于视口宽度的 HTML 元素数组。
> Returns an array of HTML elements whose width is larger than that of the viewport's.

- 使用 `HTMLElement.offsetWidth` 获取 `Document` 的宽度。
- 在 `Document.querySelectorAll()` 的结果上使用 `Array.prototype.filter()` 来检查文档中所有元素的宽度。

```js
const getElementsBiggerThanViewport = () => {
  const docWidth = document.documentElement.offsetWidth;
  return [...document.querySelectorAll('*')].filter(
    el => el.offsetWidth > docWidth
  );
};
```

```js
getElementsBiggerThanViewport(); // <div id="ultra-wide-item" />
```
