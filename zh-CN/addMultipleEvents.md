---
title: 添加多个事件监听(Add multiple listeners)
tags: browser,event
expertise: intermediate
cover: blog_images/balloons.jpg
firstSeen: 2020-10-08T00:40:30+03:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 将具有相同处理程序的多个事件侦听器添加到元素。
> Adds multiple event listeners with the same handler to an element.

- 使用 `Array.prototype.forEach()` and `EventTarget.addEventListener()` 将具有分配回调函数的多个事件侦听器添加到元素。

```js
const addMultipleListeners = (el, types, listener, options, useCapture) => {
  types.forEach(type =>
    el.addEventListener(type, listener, options, useCapture)
  );
};
```

```js
addMultipleListeners(
  document.querySelector('.my-element'),
  ['click', 'mousedown'],
  () => { console.log('hello!') }
);
```
