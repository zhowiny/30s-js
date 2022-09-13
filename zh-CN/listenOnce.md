---
title: 只监听一次事件(Listen for an event only once)
tags: browser,event
expertise: beginner
author: chalarangelo
cover: blog_images/dog-waiting.jpg
firstSeen: 2020-06-01T16:58:52+03:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 将事件侦听器添加到仅在第一次触发事件时运行回调的元素。
> Adds an event listener to an element that will only run the callback the first time the event is triggered.

- 使用 `EventTarget.addEventListener()` 将事件监听器添加到元素。
- 使用 `{ once: true }` 作为仅运行给定回调一次的选项。

```js
const listenOnce = (el, evt, fn) =>
  el.addEventListener(evt, fn, { once: true });
```

```js
listenOnce(
  document.getElementById('my-id'),
  'click',
  () => console.log('Hello world')
); // 'Hello world' 只会在第一次点击时打印
```
