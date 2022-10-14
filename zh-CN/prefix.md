---
title: CSS属性前缀(Prefix CSS property)
tags: browser
expertise: intermediate
cover: blog_images/cancel-typographer.jpg
firstSeen: 2018-03-08T15:22:54+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 基于当前浏览器为 CSS 属性添加前缀。
> Prefixes a CSS property based on the current browser.

- 在供应商前缀字符串数组上使用 `Array.prototype.findIndex()` 来测试 `Document.body` 是否在其 `CSSStyleDeclaration` 对象中定义了其中一个，否则返回 `null`。
- 使用 `String.prototype.charAt()` 和 `String.prototype.toUpperCase()` 将属性大写，这将附加到供应商前缀字符串。

```js
const prefix = prop => {
  const capitalizedProp = prop.charAt(0).toUpperCase() + prop.slice(1);
  const prefixes = ['', 'webkit', 'moz', 'ms', 'o'];
  const i = prefixes.findIndex(
    prefix =>
      typeof document.body.style[prefix ? prefix + capitalizedProp : prop] !==
      'undefined'
  );
  return i !== -1 ? (i === 0 ? prop : prefixes[i] + capitalizedProp) : null;
};
```

```js
prefix('appearance');
// 浏览器上支持'appearance'，否则为 'webkitAppearance', 'mozAppearance', 'msAppearance' 或者 'oAppearance'
```
