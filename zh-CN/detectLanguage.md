---
title: 检测语言(Detect language)
tags: browser
expertise: intermediate
cover: blog_images/accessibility.jpg
firstSeen: 2020-10-05T18:03:26+03:00
lastUpdated: 2020-10-06T18:47:16+03:00
---

# 检测当前用户的首选语言。
> Detects the preferred language of the current user.

- 如果可用，使用 `Navigator.language` 或 `Navigator.languages` 的第一个值，否则返回 `defaultLang`。
- 省略第二个参数 `defaultLang` ，以使用 `en-US` 作为默认语言代码。

```js
const detectLanguage = (defaultLang = 'en-US') =>
  navigator.language ||
  (Array.isArray(navigator.languages) && navigator.languages[0]) ||
  defaultLang;
```

```js
detectLanguage(); // 'zh'
```
