---
title: 查询字符串转对象(Query string to object)
tags: object
expertise: intermediate
cover: blog_images/dark-mode.jpg
firstSeen: 2020-10-20T20:25:32+03:00
lastUpdated: 2020-11-03T22:11:18+02:00
---

### 从给定的查询字符串或 URL 生成一个对象。
> Generates an object from the given query string or URL.

- 使用 `String.prototype.split()` 从给定的 `url` 获取参数。
- 使用 `URLSearchParams` 构造函数创建适当的对象，并使用扩展运算符 (`...`) 将其转换为键值对数组。
- 使用 `Array.prototype.reduce()` 将键值对数组转换为对象。

```js
const queryStringToObject = url =>
  [...new URLSearchParams(url.split('?')[1])].reduce(
    (a, [k, v]) => ((a[k] = v), a),
    {}
  );
```

```js
queryStringToObject('https://google.com?page=1&count=10');
// {page: '1', count: '10'}
```
