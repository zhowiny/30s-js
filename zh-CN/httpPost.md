---
title: HTTP post请求(HTTP post)
tags: browser
expertise: intermediate
cover: blog_images/boats.jpg
firstSeen: 2018-01-08T22:07:02+02:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 向传递的 URL 发出 `POST` 请求。
> Makes a `POST` request to the passed URL.

- 使用 `XMLHttpRequest` Web API 向给定的 `url` 发出 `POST` 请求。
- 使用 `setRequestHeader` 方法设置 `HTTP` 请求标头的值。
- 处理 `onload` 事件，通过调用给定的 `callback` `responseText`。
- 通过运行提供的 `err` 函数来处理 `onerror` 事件。
- 省略第四个参数 `err`，默认将错误记录到控制台的 `error` 流。

```js
const httpPost = (url, data, callback, err = console.error) => {
  const request = new XMLHttpRequest();
  request.open('POST', url, true);
  request.setRequestHeader('Content-type', 'application/json; charset=utf-8');
  request.onload = () => callback(request.responseText);
  request.onerror = () => err(request);
  request.send(data);
};
```

```js
const newPost = {
  userId: 1,
  id: 1337,
  title: 'Foo',
  body: 'bar bar bar'
};
const data = JSON.stringify(newPost);
httpPost(
  'https://jsonplaceholder.typicode.com/posts',
  data,
  console.log
); /*
Logs: {
  "userId": 1,
  "id": 1337,
  "title": "Foo",
  "body": "bar bar bar"
}
*/
httpPost(
  'https://jsonplaceholder.typicode.com/posts',
  null, // does not send a body
  console.log
); /*
Logs: {
  "id": 101
}
*/
```
