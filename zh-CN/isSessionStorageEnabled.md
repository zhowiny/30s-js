---
title: 检查 sessionStorage 是否启用(Check if sessionStorage is enabled)
tags: browser
expertise: intermediate
author: chalarangelo
cover: blog_images/flower-camera.jpg
firstSeen: 2020-12-31T13:13:47+02:00
lastUpdated: 2020-12-31T13:13:47+02:00
---

# 检查是否启用了 `sessionStorage`。
> Checks if `sessionStorage` is enabled.

- 如果所有操作成功完成，则使用 `try...catch` 块返回 `true`，否则返回 `false`。
- 使用 `Storage.setItem()` 和 `Storage.removeItem()` 测试在 `Window.sessionStorage` 中存储和删除值。

```js
const isSessionStorageEnabled = () => {
  try {
    const key = `__storage__test`;
    window.sessionStorage.setItem(key, null);
    window.sessionStorage.removeItem(key);
    return true;
  } catch (e) {
    return false;
  }
};
```

```js
isSessionStorageEnabled(); // true, if sessionStorage is accessible
```
