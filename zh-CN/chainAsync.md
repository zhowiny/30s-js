---
title: 链式异步函数(Chain async functions)
tags: function
expertise: intermediate
cover: blog_images/tram-car.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

### 链式异步函数
> Chains asynchronous functions.

- 循环遍历包含异步事件的函数数组，当每个异步事件完成时调用`next`。

```js
const chainAsync = fns => {
  let curr = 0;
  const last = fns[fns.length - 1];
  const next = () => {
    const fn = fns[curr++];
    fn === last ? fn() : fn(next);
  };
  next();
};
```

```js
chainAsync([
  next => {
    console.log('0 seconds');
    setTimeout(next, 1000);
  },
  next => {
    console.log('1 second');
    setTimeout(next, 1000);
  },
  () => {
    console.log('2 second');
  }
]);
```
