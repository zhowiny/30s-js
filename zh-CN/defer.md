---
title: 延迟函数调用(Defer function invocation)
tags: function
expertise: intermediate
cover: blog_images/cave-view.jpg
firstSeen: 2018-01-01T23:40:31+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 延迟调用函数，直到当前调用堆栈被清除。
> Defers invoking a function until the current call stack has cleared.

- 使用 `setTimeout()` 和 `1` 毫秒的超时将新事件添加到事件队列并允许渲染引擎完成其工作。
- 使用展开 (`...`) 运算符为函数提供任意数量的参数。

```js
const defer = (fn, ...args) => setTimeout(fn, 1, ...args);
```

```js
// Example A:
defer(console.log, 'a'), console.log('b'); // logs 'b' then 'a'

// Example B:
document.querySelector('#someElement').innerHTML = 'Hello';
longRunningFunction();
// 浏览器在完成之前不会更新 HTML
defer(longRunningFunction);
// 浏览器将更新 HTML 然后运行该函数
```
