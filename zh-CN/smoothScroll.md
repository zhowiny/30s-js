---
title: 元素平滑滚动进入窗口(Smooth scroll element into view)
tags: browser,css
expertise: intermediate
cover: blog_images/carrots.jpg
firstSeen: 2018-03-02T18:22:51+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 将调用它的元素平滑滚动到浏览器窗口的可见区域。
> Smoothly scrolls the element on which it's called into the visible area of the browser window.

- 使用 `Element.scrollIntoView()` 滚动元素。
- 使用 `{ behavior: 'smooth' }` 平滑滚动。

```js
const smoothScroll = element =>
  document.querySelector(element).scrollIntoView({
    behavior: 'smooth'
  });
```

```js
smoothScroll('#fooBar'); // 平滑滚动到 id 为 fooBar 的元素
smoothScroll('.fooBar');
// 平滑滚动到具有 fooBar 类的第一个元素
```
