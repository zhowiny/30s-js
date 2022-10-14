---
title: 对象是类promise(Value is promise-like)
tags: type,function,promise
expertise: intermediate
cover: blog_images/digital-nomad-13.jpg
firstSeen: 2017-12-31T14:25:43+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 检查对象是否类似 [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)。
> Checks if an object looks like a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

- 检查对象是否不是 `null`，它的 `typeof` 匹配 `object` 或 `function` 以及它是否具有 `.then` 属性，这也是一个 `function`。

```js
const isPromiseLike = obj =>
  obj !== null &&
  (typeof obj === 'object' || typeof obj === 'function') &&
  typeof obj.then === 'function';
```

```js
isPromiseLike({
  then: function() {
    return '';
  }
}); // true
isPromiseLike(null); // false
isPromiseLike({}); // false
```
