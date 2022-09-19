---
title: 重定向到URL(Redirect to URL)
tags: browser
expertise: beginner
cover: blog_images/coffee-phone-tray-2.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-20T11:46:23+03:00
---

### 重定向到指定的 URL。
> Redirects to a specified URL.

- 使用 `Window.location.href` 或 `Window.location.replace()` 重定向到 `url`。
- 传递第二个参数来模拟链接点击（`true` - 默认）或 HTTP 重定向（`false`）。

```js
const redirect = (url, asLink = true) =>
  asLink ? (window.location.href = url) : window.location.replace(url);
```

```js
redirect('https://google.com');
```
