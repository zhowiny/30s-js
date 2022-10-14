---
title: HTTP get请求(HTTP get)
tags: browser
expertise: intermediate
cover: blog_images/boat-port.jpg
firstSeen: 2018-01-08T18:21:52+02:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

# 向传递的 URL 发出 `GET` 请求。
> Makes a `GET` request to the passed URL.

- 使用 `XMLHttpRequest` Web API 向给定的 `url` 发出 `GET` 请求。
- 处理 `onload` 事件，通过调用给定的 `callback` `responseText`。
- 通过运行提供的 `err` 函数来处理 `onerror` 事件。
- 省略第三个参数 `err`，默认情况下将错误记录到控制台的 `error` 流。

```js
const httpGet = (url, callback, err = console.error) => {
  const request = new XMLHttpRequest();
  request.open('GET', url, true);
  request.onload = () => callback(request.responseText);
  request.onerror = () => err(request);
  request.send();
};
```

```js
httpGet(
  'https://jsonplaceholder.typicode.com/posts/1',
  console.log
); /*
Logs: {
  "userId": 1,
  "id": 1,
  "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
  "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
}
*/
```
