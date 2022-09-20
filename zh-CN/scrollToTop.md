---
title: 滚动到页面顶部(Scroll page to top)
tags: browser
expertise: intermediate
cover: blog_images/tranquil-lake.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 平滑滚动到页面顶部。
> Smooth-scrolls to the top of the page.

- 使用 `Document.documentElement` 或 `Document.body` 和 `Element.scrollTop` 获取与顶部的距离。
- 从顶部滚动一小部分距离。
- 使用 `Window.requestAnimationFrame()` 为滚动设置动画。
- [window.scrollTop](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/scrollTo)

```js
const scrollToTop = () => {
  const c = document.documentElement.scrollTop || document.body.scrollTop;
  if (c > 0) {
    window.requestAnimationFrame(scrollToTop);
    window.scrollTo(0, c - c / 8);
  }
};
```

```js
scrollToTop(); // 平滑滚动到页面顶部

// 等同于
window.scrollTo({ top: 0, behavior: 'smooth' });
```
