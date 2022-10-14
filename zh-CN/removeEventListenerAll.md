---
title: 从目标元素中移除事件监听器(Remove event listeners from target)
tags: browser,event
expertise: intermediate
author: chalarangelo
cover: blog_images/snowy-mountains.jpg
firstSeen: 2021-04-22T08:53:29+03:00
lastUpdated: 2021-04-22T08:53:29+03:00
---

# 从所有提供的目标元素中分离事件侦听器。
> Detaches an event listener from all the provided targets.

- 使用 `Array.prototype.forEach()` 和 `EventTarget.removeEventListener()` 将给定事件 `type` 提供的 `listener` 从所有 `targets` 中分离出来。

```js
const removeEventListenerAll = (
  targets,
  type,
  listener,
  options,
  useCapture
) => {
  targets.forEach(target =>
    target.removeEventListener(type, listener, options, useCapture)
  );
};
```

```js
const linkListener = () => console.log('Clicked a link');
document.querySelector('a').addEventListener('click', linkListener);
removeEventListenerAll(document.querySelectorAll('a'), 'click', linkListener);
```
