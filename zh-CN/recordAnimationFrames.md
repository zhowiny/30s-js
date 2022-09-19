---
title: 记录动画帧(Record animation frames)
tags: browser,recursion
expertise: intermediate
cover: blog_images/curve.jpg
firstSeen: 2018-02-28T08:19:07+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

### 在每个动画帧上调用提供的回调。
> Invokes the provided callback on each animation frame.

- 使用递归。
- 如果 `running` 为 `true`，则继续调用 `Window.requestAnimationFrame()`，它会调用提供的回调。
- 使用 `start` 和 `stop` 两种方法返回一个对象，以允许手动控制记录。
- 省略第二个参数 `autoStart`，以便在调用函数时隐式调用 `start`。

```js
const recordAnimationFrames = (callback, autoStart = true) => {
  let running = false,
    raf;
  const stop = () => {
    if (!running) return;
    running = false;
    cancelAnimationFrame(raf);
  };
  const start = () => {
    if (running) return;
    running = true;
    run();
  };
  const run = () => {
    raf = requestAnimationFrame(() => {
      callback();
      if (running) run();
    });
  };
  if (autoStart) start();
  return { start, stop };
};
```

```js
const cb = () => console.log('Animation frame fired');
const recorder = recordAnimationFrames(cb);
// 在每个动画帧上输出 'Animation frame fired'
recorder.stop(); // 停止输出日志
recorder.start(); // 再次开始
const recorder2 = recordAnimationFrames(cb, false);
// 需要显式调用 `start` 才能开始记录帧
```
