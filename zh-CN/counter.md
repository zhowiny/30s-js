---
title: 计数器(Counter)
tags: browser
expertise: advanced
cover: blog_images/touch-flower.jpg
firstSeen: 2018-05-06T17:55:46+03:00
lastUpdated: 2020-11-01T20:50:57+02:00
---

### 为指定的选择器创建一个具有指定范围、步长和持续时间的计数器。
> Creates a counter with the specified range, step and duration for the specified selector.

- 检查 `step` 是否有正确的符号并相应地改变它。
- 使用 `setInterval()` 结合 `Math.abs()` 和 `Math.floor()` 来计算每次新文本绘制之间的时间。
- 使用 `Document.querySelector()`、`Element.innerHTML` 来更新所选元素的值。
- 省略第四个参数，`step`，使用默认的 step `1`。
- 省略第五个参数，`duration`，使用默认持续时间 `2000` 毫秒。
- **注意: 请注意每次调用回调函数之间经过的实际时间可能会比给定的 delay 长;[参考setInterval(MDN)](https://developer.mozilla.org/zh-CN/docs/Web/API/setInterval#%E5%BB%B6%E8%BF%9F%E9%99%90%E5%88%B6)**

```js
const counter = (selector, start, end, step = 1, duration = 2000) => {
  let current = start,
    _step = (end - start) * step < 0 ? -step : step,
    timer = setInterval(() => {
      current += _step;
      document.querySelector(selector).innerHTML = current;
      if (current >= end) document.querySelector(selector).innerHTML = end;
      if (current >= end) clearInterval(timer);
    }, Math.abs(Math.floor(duration / (end - start))));
  return timer;
};
```

```js
counter('#my-id', 1, 1000, 5, 2000);
// 为 id="my-id" 的元素创建一个 2 秒计时器
```
