---
title: 当前URL(Current URL)
tags: browser
expertise: beginner
cover: blog_images/tropical-bike.jpg
firstSeen: 2017-12-18T11:05:03+02:00
lastUpdated: 2020-10-20T11:46:23+03:00
---

# 返回当前 URL。
> Returns the current URL.

- 使用 `Window.location.href` 获取当前 URL。

```js
const currentURL = () => window.location.href;
```

```js
currentURL(); // 'https://www.google.com/'
```
