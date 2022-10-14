---
title: 向元素添加事件监听器(Add event listener to element)
tags: browser,event
expertise: intermediate
cover: blog_images/wooden-bowl.jpg
firstSeen: 2018-01-05T14:33:48+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

# 将事件侦听器添加到能够使用事件委托的元素。
> Adds an event listener to an element with the ability to use event delegation.

- 使用 `EventTarget.addEventListener()` 将事件监听器添加到元素。
- 如果有提供给选项对象的 `target` 属性，请确保事件目标与指定的目标匹配，然后通过提供正确的 `this` 上下文来调用回调。
- 省略 `opts` 以默认为非委托行为和事件冒泡。
- 返回对自定义委托函数的引用，以便可以与 [`off`](off) 一起使用。

```js
const on = (el, evt, fn, opts = {}) => {
  const delegatorFn = e =>
    e.target.matches(opts.target) && fn.call(e.target, e);
  el.addEventListener(
    evt,
    opts.target ? delegatorFn : fn,
    opts.options || false
  );
  if (opts.target) return delegatorFn;
};
```

```js
const fn = () => console.log('!');
on(document.body, 'click', fn); // 点击`body`后打印 '!'
on(document.body, 'click', fn, { target: 'p' });
// 点击`body`中的`p`元素后打印 '!'
on(document.body, 'click', fn, { options: true });
// 使用捕获而不是冒泡
```
