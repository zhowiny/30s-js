---
title: 检查是否启用了 localStorage(Check if localStorage is enabled)
tags: browser
expertise: intermediate
author: chalarangelo
cover: blog_images/guitar-living-room.jpg
firstSeen: 2020-12-31T13:13:47+02:00
lastUpdated: 2020-12-31T13:13:47+02:00
---
# 检查是否启用了 `localStorage`。
> Checks if `localStorage` is enabled.

- 如果所有操作成功完成，则使用 `try...catch` 块返回 `true`，否则返回 `false`。
- 使用 `Storage.setItem()` 和 `Storage.removeItem()` 测试在 `Window.localStorage` 中存储和删除值。

```js
const isLocalStorageEnabled = () => {
  try {
    const key = `__storage__test`;
    window.localStorage.setItem(key, null);
    window.localStorage.removeItem(key);
    return true;
  } catch (e) {
    return false;
  }
};
```

```js
isLocalStorageEnabled(); // true, 如果 localStorage 可以访问
```
