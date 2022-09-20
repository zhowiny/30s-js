---
title: 序列化表单(Serialize form)
tags: browser,string
expertise: intermediate
cover: blog_images/down-the-stream.jpg
firstSeen: 2019-03-13T14:29:45+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 将一组表单元素编码为查询字符串。
> Encodes a set of form elements as a query string.

- 使用 `FormData` 构造函数将 HTML `form` 转换为 `FormData`。
- 使用 `Array.from()` 转换为数组，将 map 函数作为第二个参数传递。
- 使用 `Array.prototype.map()` 和 `encodeURIComponent()` 对每个字段的值进行编码。
- 使用带有适当参数的 `Array.prototype.join()` 来生成适当的查询字符串。

```js
const serializeForm = form =>
  Array.from(new FormData(form), field =>
    field.map(encodeURIComponent).join('=')
  ).join('&');
```

```js
serializeForm(document.querySelector('#form'));
// email=test%40email.com&name=Test%20Name
```
