---
title: HTTP delete请求(HTTP delete)
tags: browser
expertise: intermediate
cover: blog_images/beach-from-above.jpg
firstSeen: 2020-04-16T11:21:33+03:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 向传递的 URL 发出 `DELETE` 请求。
> Makes a `DELETE` request to the passed URL.

- 使用 `XMLHttpRequest` Web API 向给定的 `url` 发出 `DELETE` 请求。
- 通过运行提供的 `callback` 函数来处理 `onload` 事件。
- 通过运行提供的 `err` 函数来处理 `onerror` 事件。
- 省略第三个参数 `err` 以默认将请求记录到控制台的错误流中。

```js
const httpDelete = (url, callback, err = console.error) => {
  const request = new XMLHttpRequest();
  request.open('DELETE', url, true);
  request.onload = () => callback(request);
  request.onerror = () => err(request);
  request.send();
};
```

```js
httpDelete('https://jsonplaceholder.typicode.com/posts/1', request => {
  console.log(request.responseText);
}); // Logs: {}
```
