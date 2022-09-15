---
title: 观察元素变化(Observe element mutations)
tags: browser,event
expertise: advanced
cover: blog_images/blue-sunrise.jpg
firstSeen: 2018-01-13T14:58:52+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

### 创建一个新的 `MutationObserver` 并为指定元素上的每个变化运行提供的回调。
> Creates a new `MutationObserver` and runs the provided callback for each mutation on the specified element.

- 使用 [`MutationObserver`](https://developer.mozilla.org/zh-CN/docs/Web/API/MutationObserver) 观察给定元素的突变。
- 使用 `Array.prototype.forEach()` 为观察到的每个突变运行回调。
- 省略第三个参数 `options` 以使用默认的 [options](https://developer.mozilla.org/zh-CN/docs/Web/API/MutationObserver#MutationObserverInit)（全部为 `true`）。

```js
const observeMutations = (element, callback, options) => {
  const observer = new MutationObserver(mutations =>
    mutations.forEach(m => callback(m))
  );
  observer.observe(
    element,
    Object.assign(
      {
        childList: true,
        attributes: true,
        attributeOldValue: true,
        characterData: true,
        characterDataOldValue: true,
        subtree: true,
      },
      options
    )
  );
  return observer;
};
```

```js
const obs = observeMutations(document, console.log);
// 打印页面上发生的所有变化
obs.disconnect();
// 停止观察者并停止在页面上打印变化
```
