---
title: 复制到剪贴板(Copy to clipboard)
tags: browser,string,event
expertise: advanced
cover: blog_images/typing.jpg
firstSeen: 2017-12-31T11:40:33+02:00
lastUpdated: 2022-01-11T09:32:04+02:00
---

# 将字符串复制到剪贴板。
仅作为用户操作的结果起作用（即在 `click` 事件侦听器中）。

> Copies a string to the clipboard.
> Only works as a result of user action (i.e. inside a `click` event listener).

- 创建一个新的 `<textarea>` 元素，用提供的数据填充它并将其添加到 HTML 文档中。
- 使用 `Selection.getRangeAt()` 存储所选范围（如果有）。
- 使用 `Document.execCommand()` 复制到剪贴板。
- 从 HTML 文档中删除 `<textarea>` 元素。
- 最后，使用 `Selection.addRange()` 恢复原始选定范围（如果有）。
- **注意：**您可以在大多数当前浏览器中使用异步 [Clipboard API](https://developer.mozilla.org/en-US/docs/Web/API/Clipboard_API)。 您可以在 [copyToClipboardAsync 片段](/js/s/copy-to-clipboard-async) 中找到有关它的更多信息。

```js
const copyToClipboard = str => {
  const el = document.createElement('textarea');
  el.value = str;
  el.setAttribute('readonly', '');
  el.style.position = 'absolute';
  el.style.left = '-9999px';
  document.body.appendChild(el);
  const selected =
    document.getSelection().rangeCount > 0
      ? document.getSelection().getRangeAt(0)
      : false;
  el.select();
  document.execCommand('copy');
  document.body.removeChild(el);
  if (selected) {
    document.getSelection().removeAllRanges();
    document.getSelection().addRange(selected);
  }
};
```

```js
copyToClipboard('Lorem ipsum'); // 'Lorem ipsum' copied to clipboard.
```
