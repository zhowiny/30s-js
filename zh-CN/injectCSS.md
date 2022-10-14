---
title: 注入 CSS(Inject CSS)
tags: browser,css
expertise: intermediate
cover: blog_images/dark-leaves-5.jpg
firstSeen: 2020-10-15T22:18:00+03:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 将给定的 CSS 代码注入当前文档
> Injects the given CSS code into the current document

- 使用 `Document.createElement()` 创建一个新的 `style` 元素并将其类型设置为 `text/css`。
- 使用 `Element.innerText` 将值设置为给定的 CSS 字符串。
- 使用 `Document.head` 和 `Element.appendChild()` 将新元素附加到文档头部。
- 返回新创建的 `style` 元素。

```js
const injectCSS = css => {
  let el = document.createElement('style');
  el.type = 'text/css';
  el.innerText = css;
  document.head.appendChild(el);
  return el;
};
```

```js
injectCSS('body { background-color: #000 }');
// '<style type="text/css">body { background-color: #000 }</style>'
```
