---
title: 创建事件中心(订阅/发布)(Create event hub)
tags: browser,event
expertise: advanced
cover: blog_images/city-view.jpg
firstSeen: 2018-01-05T15:07:26+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

### 使用 `emit`、`on` 和 `off` 方法创建一个 pub/sub ([publish–subscribe](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern)) 事件中心。
> Creates a pub/sub ([publish–subscribe](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern)) event hub with `emit`, `on`, and `off` methods.

- 使用带有 `null` 参数的 `Object.create()` 创建一个不从 `Object.prototype` 继承属性的空 `hub` 对象。
- 对于 `emit`，根据 `event` 参数解析处理程序数组，然后通过将数据作为参数传入，使用 `Array.prototype.forEach()` 运行每个处理程序。
- 对于 `on`，如果事件尚不存在，则为其创建一个数组，然后使用 `Array.prototype.push()` 添加处理函数到数组。
- 对于 `off`，使用 `Array.prototype.findIndex()` 在事件数组中查找处理函数的索引，并使用 `Array.prototype.splice()` 将其删除。

```js
const createEventHub = () => ({
  hub: Object.create(null),
  emit(event, data) {
    (this.hub[event] || []).forEach(handler => handler(data));
  },
  on(event, handler) {
    if (!this.hub[event]) this.hub[event] = [];
    this.hub[event].push(handler);
  },
  off(event, handler) {
    const i = (this.hub[event] || []).findIndex(h => h === handler);
    if (i > -1) this.hub[event].splice(i, 1);
    if (this.hub[event].length === 0) delete this.hub[event];
  }
});
```

```js
const handler = data => console.log(data);
const hub = createEventHub();
let increment = 0;

// 订阅：监听不同类型的事件
hub.on('message', handler);
hub.on('message', () => console.log('Message event fired'));
hub.on('increment', () => increment++);

// 发布：发出事件以调用所有订阅它们的处理程序，将数据作为参数传递给它们
hub.emit('message', 'hello world'); // 打印 'hello world' 和 'Message event fired'
hub.emit('message', { hello: 'world' }); // 打印这个对象和 'Message event fired'
hub.emit('increment'); // `increment`  现在变量是 1

// 取消订阅：停止特定的处理程序监听 `message` 事件
hub.off('message', handler);
```
