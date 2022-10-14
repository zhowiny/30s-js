---
title: 用户偏好亮色主题(User prefers light color scheme)
tags: browser
expertise: intermediate
author: chalarangelo
cover: blog_images/dark-mode.jpg
firstSeen: 2020-05-04T12:50:35+03:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 检查用户配色方案首选项是否为 `light`。
> Checks if the user color scheme preference is `light`.

- 使用 `Window.matchMedia()` 和适当的媒体查询来检查用户配色方案偏好。

```js
const prefersLightColorScheme = () =>
  window &&
  window.matchMedia &&
  window.matchMedia('(prefers-color-scheme: light)').matches;
```

```js
prefersLightColorScheme(); // true
```
