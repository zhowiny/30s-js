---
title: 防抖Promise(Debounce promise)
tags: function,promise
expertise: advanced
excerpt: Creates a debounced function that returns a promise.
cover: blog_images/ice.jpg
firstSeen: 2020-10-10T21:09:04+03:00
lastUpdated: 2020-10-19T18:51:03+03:00
---

### 创建一个返回`Promise`的去抖动函数，但延迟调用提供的函数，直到自上次调用它以来至少经过 `ms` 毫秒。
在此期间返回的所有`Promise`都将返回相同的数据。

> Creates a debounced function that returns a promise, but delays invoking the provided function until at least `ms` milliseconds have elapsed since the last time it was invoked.
> All promises returned during this time will return the same data.

- 每次调用去抖动函数时，使用 `clearTimeout()` 清除当前挂起的超时，并使用 `setTimeout()` 创建一个新的超时，该超时会延迟调用该函数，直到至少经过 `ms` 毫秒。
- 使用 `Function.prototype.apply()` 将 `this` 上下文应用到函数并提供必要的参数。
- 创建一个新的 `Promise` 并将其 `resolve` 和 `reject` 回调添加到 `pending` Promise堆栈。
- 当 `setTimeout()` 被调用时，复制当前堆栈（因为它可以在提供的函数调用和它的分辨率之间改变），清除它并调用提供的函数。
- 当提供的函数解析/拒绝时，使用返回的数据解析/拒绝堆栈中的所有`Promise`（在调用函数时复制）。
- 省略第二个参数 `ms`，将超时设置为默认值 `0` 毫秒。

```js
const debouncePromise = (fn, ms = 0) => {
  let timeoutId;
  const pending = [];
  return (...args) =>
    new Promise((res, rej) => {
      clearTimeout(timeoutId);
      timeoutId = setTimeout(() => {
        const currentPending = [...pending];
        pending.length = 0;
        Promise.resolve(fn.apply(this, args)).then(
          data => {
            currentPending.forEach(({ resolve }) => resolve(data));
          },
          error => {
            currentPending.forEach(({ reject }) => reject(error));
          }
        );
      }, ms);
      pending.push({ resolve: res, reject: rej });
    });
};
```

```js
const fn = arg => new Promise(resolve => {
  setTimeout(resolve, 1000, ['resolved', arg]);
});
const debounced = debouncePromise(fn, 200);
debounced('foo').then(console.log);
debounced('bar').then(console.log);
// 将会打印 ['resolved', 'bar'] 2次
```
