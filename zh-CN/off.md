---
title: 从元素中移除事件监听器(Remove event listener from element)
tags: browser,event
expertise: intermediate
cover: blog_images/mug-flower-book.jpg
firstSeen: 2018-01-05T14:33:48+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 从元素中移除事件监听器。
> Removes an event listener from an element.

- 使用 `EventTarget.removeEventListener()` 从元素中移除事件监听器。
- 省略第四个参数 `opts` 以使用 `false` 或根据添加事件侦听器时使用的选项指定它。

```js
const off = (el, evt, fn, opts = false) =>
  el.removeEventListener(evt, fn, opts);
```

```js
const fn = () => console.log('!');
document.body.addEventListener('click', fn);
off(document.body, 'click', fn); // 点击页面后,不再打印 `!`
```
