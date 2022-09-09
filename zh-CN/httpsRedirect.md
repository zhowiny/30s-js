---
title: 重定向到 HTTPS(Redirect to HTTPS)
tags: browser
expertise: intermediate
cover: blog_images/blue-lake.jpg
firstSeen: 2017-12-21T08:33:56+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 如果页面当前在 HTTP 中，则将页面重定向到 HTTPS。
> Redirects the page to HTTPS if it's currently in HTTP.

- 使用 `location.protocol` 获取当前使用的协议。
- 如果不是 HTTPS，使用 `location.replace()` 将现有页面替换为 HTTPS 版本的页面。
- 使用 `location.href` 获取完整地址，使用 `String.prototype.split()` 拆分它并删除 URL 的协议部分。
- 请注意，按下后退按钮不会将其返回到 HTTP 页面，因为它已在历史记录中被替换。

```js
const httpsRedirect = () => {
  if (location.protocol !== 'https:')
    location.replace('https://' + location.href.split('//')[1]);
};
```

```js
httpsRedirect();
// 如果你在 http://mydomain.com, 你会被重定向到 https://mydomain.com
```
