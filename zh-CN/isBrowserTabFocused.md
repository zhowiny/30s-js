---
title: 检查浏览器选项卡是否聚焦(Check if browser tab is focused)
tags: browser
expertise: beginner
cover: blog_images/overgrown.jpg
firstSeen: 2018-04-15T19:18:44+03:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 检查页面的浏览器选项卡是否获得焦点。
> Checks if the browser tab of the page is focused.

- 使用 [Page Visibility API](https://developer.mozilla.org/en-US/docs/Web/API/Page_Visibility_API) 引入的 `Document.hidden` 属性来检查页面的浏览器选项卡 可见或隐藏。
- [Page Visibility API 教程(阮一峰)](http://www.ruanyifeng.com/blog/2018/10/page_visibility_api.html)

```js
const isBrowserTabFocused = () => !document.hidden;
```

```js
isBrowserTabFocused(); // true
```
