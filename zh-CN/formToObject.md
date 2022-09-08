---
title: Form表单转对象(Form to object)
tags: browser,object
expertise: intermediate
cover: blog_images/sail-away-2.jpg
firstSeen: 2019-03-13T14:50:06+02:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 将一组表单元素编码为 `object`。
> Encodes a set of form elements as an `object`.

- 使用 `FormData` 构造函数将 HTML `form` 转换为 `FormData` 和 `Array.from()` 转换为数组。
- 使用 `Array.prototype.reduce()` 从数组中收集对象。

```js
const formToObject = form =>
  Array.from(new FormData(form)).reduce(
    (acc, [key, value]) => ({
      ...acc,
      [key]: value
    }),
    {}
  );
```

```js
formToObject(document.querySelector('#form'));
// { email: 'test@email.com', name: 'Test Name' }
```
