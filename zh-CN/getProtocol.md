---
title: 当前页面协议(Current page protocol)
tags: browser
expertise: beginner
cover: blog_images/bamboo-lamp.jpg
firstSeen: 2020-10-07T01:40:53+03:00
lastUpdated: 2020-10-20T11:46:23+03:00
---

### 获取当前页面使用的协议。
> Gets the protocol being used on the current page.

- 使用 `Window.location.protocol` 获取当前页面的协议（`http:` 或 `https:`）。

```js
const getProtocol = () => window.location.protocol;
```

```js
getProtocol(); // 'https:'
```
