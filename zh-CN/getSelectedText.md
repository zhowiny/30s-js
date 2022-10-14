---
title: 获取选中的文本(Get selected text)
tags: browser
expertise: beginner
author: chalarangelo
cover: blog_images/white-tablet-2.jpg
firstSeen: 2020-08-07T15:34:53+03:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

# 获取当前选中的文本。
> Gets the currently selected text.

- 使用 `Window.getSelection()` 和 `Selection.toString()` 获取当前选择的文本。

```js
const getSelectedText = () => window.getSelection().toString();
```

```js
getSelectedText(); // 'Lorem ipsum'
```
