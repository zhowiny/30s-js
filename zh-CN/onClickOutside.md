---
title: 点击元素外部(Handle click outside)
tags: browser,event
expertise: intermediate
author: chalarangelo
cover: blog_images/interior-13.jpg
firstSeen: 2021-01-06T13:57:56+02:00
lastUpdated: 2021-01-06T13:57:56+02:00
---

### 每当用户在指定元素之外单击时运行回调。
> Runs the callback whenever the user clicks outside of the specified element.

- 使用 `EventTarget.addEventListener()` 来监听 `'click'` 事件。
- 使用 `Node.contains()` 检查 `Event.target` 是否是 `element` 的后代，如果不是则运行 `callback`。

```js
const onClickOutside = (element, callback) => {
  document.addEventListener('click', e => {
    if (!element.contains(e.target)) callback();
  });
};
```

```js
onClickOutside('#my-element', () => console.log('Hello'));
// 每当用户在#my-element 之外单击时，都会打印 `Hello`
```
