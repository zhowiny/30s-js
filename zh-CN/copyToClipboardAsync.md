---
title: 异步复制到剪贴板(Copy to clipboard async)
tags: browser,string,promise
expertise: advanced
cover: blog_images/typing.jpg
firstSeen: 2022-01-11T05:00:00-04:00
---

### 将字符串复制到剪贴板，返回一个在剪贴板内容更新时 `resolve` 的 `Promise`。
> Copies a string to the clipboard, returning a promise that resolves when the clipboard's contents have been updated.

- 检查 [Clipboard API](https://developer.mozilla.org/en-US/docs/Web/API/Clipboard_API) 是否可用。 使用 `if` 语句确保 `Navigator`、`Navigator.clipboard` 和 `Navigator.clipboard.writeText` 是真实的。
- 使用 `Clipboard.writeText()` 将给定值 `str` 写入剪贴板。
- 返回 `Clipboard.writeText()` 的结果，这是一个在剪贴板内容更新时解决的承诺。
- 如果剪贴板 API 不可用，请使用 `Promise.reject()` 以适当的消息拒绝。
- **注意：** 如果您需要支持旧版浏览器，您可能需要使用 `Document.execCommand()` 代替。 您可以在 [copyToClipboard 片段](/js/s/copy-to-clipboard) 中找到有关它的更多信息。

```js
const copyToClipboardAsync = str => {
  if (navigator && navigator.clipboard && navigator.clipboard.writeText)
    return navigator.clipboard.writeText(str);
  return Promise.reject('The Clipboard API is not available.');
};
```

```js
copyToClipboardAsync('Lorem ipsum'); // 'Lorem ipsum' copied to clipboard.
```
