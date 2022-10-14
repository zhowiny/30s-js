---
title: 在 HTML 元素上触发事件(Trigger event on HTML element)
tags: browser,event
expertise: intermediate
cover: blog_images/cloudy-mountaintop-2.jpg
firstSeen: 2018-06-19T20:57:58+03:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

# 在给定元素上触发特定事件，可选择传递自定义数据。
> Triggers a specific event on a given element, optionally passing custom data.

- 使用 `CustomEvent` 构造函数从指定的 `eventType` 和详细信息创建事件。
- 使用 `EventTarget.dispatchEvent()` 在给定元素上触发新创建的事件。
- 如果您不想将自定义数据传递给触发的事件，请省略第三个参数 `detail`。

```js
const triggerEvent = (el, eventType, detail) =>
  el.dispatchEvent(new CustomEvent(eventType, { detail }));
```

```js
triggerEvent(document.getElementById('myId'), 'click');
triggerEvent(document.getElementById('myId'), 'click', { username: 'bob' });
```
