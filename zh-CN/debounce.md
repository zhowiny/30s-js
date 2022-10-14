---
title: 函数防抖(Debounce function)
tags: function
expertise: intermediate
cover: blog_images/solitude-beach.jpg
firstSeen: 2018-01-28T15:18:26+02:00
lastUpdated: 2021-10-13T19:29:39+02:00
---

# 创建一个去抖动函数，该函数延迟调用提供的函数，直到自上次调用以来至少经过 `ms` 毫秒。
> Creates a debounced function that delays invoking the provided function until at least `ms` milliseconds have elapsed since its last invocation.

- 每次调用去抖动函数时，使用 `clearTimeout()` 清除当前挂起的超时。 使用 `setTimeout()` 创建一个新的超时，该超时会延迟调用该函数，直到至少经过 `ms` 毫秒。
- 使用 `Function.prototype.apply()` 将 `this` 上下文应用到函数并提供必要的参数。
- 省略第二个参数 `ms`，将超时设置为默认值 `0` 毫秒。

```js
const debounce = (fn, ms = 0) => {
  let timeoutId;
  return function(...args) {
    clearTimeout(timeoutId);
    timeoutId = setTimeout(() => fn.apply(this, args), ms);
  };
};
```

```js
window.addEventListener(
  'resize',
  debounce(() => {
    console.log(window.innerWidth);
    console.log(window.innerHeight);
  }, 250)
); // 最多每 250 毫秒打印一次窗口尺寸
```
