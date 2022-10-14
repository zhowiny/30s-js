---
title: 将事件监听添加到所有目标(Add event listener to all targets)
tags: browser,event
expertise: intermediate
author: chalarangelo
cover: blog_images/red-mountain.jpg
firstSeen: 2021-04-22T08:53:29+03:00
lastUpdated: 2021-04-22T08:53:29+03:00
---

# 将事件侦听器附加到所有提供的目标。
> Attaches an event listener to all the provided targets.

- 使用 `Array.prototype.forEach()` 和 `EventTarget.addEventListener()`, 将给定事件`type`的提供`listener`附加到所有`targets`。

```js
const addEventListenerAll = (targets, type, listener, options, useCapture) => {
  targets.forEach(target =>
    target.addEventListener(type, listener, options, useCapture)
  );
};
```

```js
addEventListenerAll(document.querySelectorAll('a'), 'click', () =>
  console.log('点击了一个链接')
);
// 每当单击任何`a`元素时打印“点击了一个链接”
```
