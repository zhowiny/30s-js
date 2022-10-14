---
title: 环境是浏览器(Environment is browser)
tags: browser,node
expertise: intermediate
cover: blog_images/travel-mug-3.jpg
firstSeen: 2018-03-19T04:50:55+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 确定当前运行环境是否是浏览器，以便前端模块可以在服务器（节点）上运行而不会引发错误。
> Determines if the current runtime environment is a browser so that front-end modules can run on the server (Node) without throwing errors.

- 在 `Window` 和 `Document` 的 `typeof` 值上使用 `Array.prototype.includes()`（全局变量通常仅在浏览器环境中可用，除非它们被明确定义），如果有则返回 `true` 其中是“未定义”。
- `typeof` 允许检查全局变量是否存在而不抛出 `ReferenceError`。
- 如果它们都不是 `undefined`，则假定当前环境是浏览器。

```js
const isBrowser = () => ![typeof window, typeof document].includes('undefined');
```

```js
isBrowser(); // true (browser)
isBrowser(); // false (Node)
```
