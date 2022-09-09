---
title: 滚动位置(Scroll position)
tags: browser
expertise: intermediate
cover: blog_images/tranquil-lake.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 返回当前页面的滚动位置。
> Returns the scroll position of the current page.

- 如果已定义，则使用 `Window.pageXOffset` 和 `Window.pageYOffset`，否则使用 `Element.scrollLeft` 和 `Element.scrollTop`。
- 省略单个参数 `el` 以使用全局 `Window` 对象。

```js
const getScrollPosition = (el = window) => ({
  x: el.pageXOffset !== undefined ? el.pageXOffset : el.scrollLeft,
  y: el.pageYOffset !== undefined ? el.pageYOffset : el.scrollTop
});
```

```js
getScrollPosition(); // {x: 0, y: 200}
```
