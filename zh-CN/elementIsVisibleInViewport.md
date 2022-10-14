---
title: 元素在视口中可见(Element is visible in viewport)
tags: browser
expertise: intermediate
cover: blog_images/flower-portrait-1.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 检查指定的元素是否在视口中可见。
> Checks if the element specified is visible in the viewport.

- 使用 `Element.getBoundingClientRect()`、`Window.innerWidth` 和 `Window.innerHeight` 来确定给定元素是否在视口中可见。
- 省略第二个参数以确定元素是否完全可见，或指定 `true` 以确定它是否部分可见。
- **注** 其他方式：[IntersectionObserver](https://developer.mozilla.org/zh-CN/docs/Web/API/IntersectionObserver)

```js
const elementIsVisibleInViewport = (el, partiallyVisible = false) => {
  const { top, left, bottom, right } = el.getBoundingClientRect();
  const { innerHeight, innerWidth } = window;
  return partiallyVisible
    ? ((top > 0 && top < innerHeight) ||
        (bottom > 0 && bottom < innerHeight)) &&
        ((left > 0 && left < innerWidth) || (right > 0 && right < innerWidth))
    : top >= 0 && left >= 0 && bottom <= innerHeight && right <= innerWidth;
};
```

```js
// e.g. 100x100 视口 和 一个在 {top: -1, left: 0, bottom: 9, right: 10} 位置 10x10px 的元素
elementIsVisibleInViewport(el); // false - (不完全可见)
elementIsVisibleInViewport(el, true); // true - (部分可见)
```
