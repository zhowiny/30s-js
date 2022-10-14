---
title: HTTP put请求(HTTP put)
tags: browser
expertise: intermediate
cover: blog_images/bridge.jpg
firstSeen: 2020-04-16T11:21:33+03:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

# 向传递的 URL 发出 `PUT` 请求。
> Makes a `PUT` request to the passed URL.

- 使用 `XMLHttpRequest` web api 向给定的 `url` 发出 `PUT` 请求。
- 使用 `setRequestHeader` 方法设置 `HTTP` 请求标头的值。
- 通过运行提供的 `callback` 函数来处理 `onload` 事件。
- 通过运行提供的 `err` 函数来处理 `onerror` 事件。
- 省略最后一个参数 `err` 以默认将请求记录到控制台的错误流中。

```js
const httpPut = (url, data, callback, err = console.error) => {
  const request = new XMLHttpRequest();
  request.open('PUT', url, true);
  request.setRequestHeader('Content-type', 'application/json; charset=utf-8');
  request.onload = () => callback(request);
  request.onerror = () => err(request);
  request.send(data);
};
```

```js
const password = 'fooBaz';
const data = JSON.stringify({
  id: 1,
  title: 'foo',
  body: 'bar',
  userId: 1
});
httpPut('https://jsonplaceholder.typicode.com/posts/1', data, request => {
  console.log(request.responseText);
}); /*
Logs: {
  id: 1,
  title: 'foo',
  body: 'bar',
  userId: 1
}
*/
```
