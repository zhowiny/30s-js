---
title: 监听滚动停止(Handle scroll stop)
tags: browser,event
expertise: intermediate
author: chalarangelo
cover: blog_images/flower-pond.jpg
firstSeen: 2021-01-07T00:31:14+02:00
lastUpdated: 2021-01-07T00:31:14+02:00
---

# 每当用户停止滚动时运行回调。
> Runs the callback whenever the user has stopped scrolling.

- 使用 `EventTarget.addEventListener()` 来监听 `'scroll'` 事件。
- 使用 `setTimeout()` 等待 `150` ms 直到调用给定的 `callback`。
- 如果在 `150` 毫秒内触发了新的 `'scroll'` 事件，请使用 `clearTimeout()` 清除超时。

```js
const onScrollStop = callback => {
  let isScrolling;
  window.addEventListener(
    'scroll',
    e => {
      clearTimeout(isScrolling);
      isScrolling = setTimeout(() => {
        callback();
      }, 150);
    },
    false
  );
};
```

```js
onScrollStop(() => {
  console.log('用户已停止滚动');
});
```
