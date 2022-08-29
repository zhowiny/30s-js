---
title: 空值参数合并工厂函数(Argument coalescing factory)
tags: function,type
expertise: intermediate
cover: blog_images/coffee-phone-tray.jpg
firstSeen: 2017-12-18T12:15:36+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 自定义一个合并函数，该函数根据给定的验证器返回第一个参数为 `true` 。
> Customizes a coalesce function that returns the first argument which is `true` based on the given validator.

- 使用 `Array.prototype.find()` 从提供的参数验证函数 `valid` 返回第一个返回 `true` 的参数。

```js
const coalesceFactory = valid => (...args) => args.find(valid);
```

```js
const customCoalesce = coalesceFactory(
  v => ![null, undefined, '', NaN].includes(v)
);
customCoalesce(undefined, null, NaN, '', 'Waldo'); // 'Waldo'
```
