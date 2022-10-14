---
title: 节流函数(Throttle function)
tags: function
expertise: advanced
cover: blog_images/waves-from-above.jpg
firstSeen: 2018-01-28T15:23:01+02:00
lastUpdated: 2021-10-13T19:29:39+02:00
---

# 创建一个节流函数，每 `wait` 毫秒最多只调用一次提供的函数
> Creates a throttled function that only invokes the provided function at most once per every `wait` milliseconds

- 使用 `setTimeout()` 和 `clearTimeout()` 来限制给定的方法，`fn`。
- 使用 `Function.prototype.apply()` 将 `this` 上下文应用到函数并提供必要的 `arguments`。
- 使用 `Date.now()` 来跟踪上次调用节流函数的时间。
- 使用变量 `inThrottle` 来防止在第一次执行 `fn` 和下一个循环之间出现竞争条件。
- 省略第二个参数 `wait`，将超时设置为默认值 `0` 毫秒。

```js
const throttle = (fn, wait) => {
  let inThrottle, lastFn, lastTime;
  return function() {
    const context = this,
      args = arguments;
    if (!inThrottle) {
      fn.apply(context, args);
      lastTime = Date.now();
      inThrottle = true;
    } else {
      clearTimeout(lastFn);
      lastFn = setTimeout(function() {
        if (Date.now() - lastTime >= wait) {
          fn.apply(context, args);
          lastTime = Date.now();
        }
      }, Math.max(wait - (Date.now() - lastTime), 0));
    }
  };
};
```

```js
window.addEventListener(
  'resize',
  throttle(function(evt) {
    console.log(window.innerWidth);
    console.log(window.innerHeight);
  }, 250)
); // 最多每 250 毫秒日志输出一次窗口尺寸
```
