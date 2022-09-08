---
title: 切换全屏模式(Toggle fullscreen mode)
tags: browser
expertise: intermediate
cover: blog_images/antelope.jpg
firstSeen: 2020-10-04T16:48:00+03:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 在全屏模式下打开或关闭元素。
> Opens or closes an element in fullscreen mode.

- 使用 `Document.querySelector()` 和 `Element.requestFullscreen()` 全屏打开给定元素。
- 使用 `Document.exitFullscreen()` 退出全屏模式。
- 省略第二个参数 `el`，以使用 `body` 作为默认元素。
- 省略第一个元素 `mode`，默认以全屏模式打开元素。

```js
const fullscreen = (mode = true, el = 'body') =>
  mode
    ? document.querySelector(el).requestFullscreen()
    : document.exitFullscreen();
```

```js
fullscreen(); // 在全屏模式打开 `body`
fullscreen(false); // 退出全屏模式
```
