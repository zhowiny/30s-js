---
title: URL 参数作转为对象(URL parameters as object)
tags: browser,string,regexp
expertise: intermediate
author: chalarangelo
cover: blog_images/compass.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 创建一个包含当前 URL 参数的对象。
> Creates an object containing the parameters of the current URL.

- 使用 `String.prototype.match()` 和适当的正则表达式来获取所有键值对。
- 使用 `Array.prototype.reduce()` 将它们映射并组合成一个对象。
- 将 `location.search` 作为参数传递给当前的 `url`。

```js
const getURLParameters = url =>
  (url.match(/([^?=&]+)(=([^&]*))/g) || []).reduce(
    (a, v) => (
      (a[v.slice(0, v.indexOf('='))] = v.slice(v.indexOf('=') + 1)), a
    ),
    {}
  );
```

```js
getURLParameters('google.com'); // {}
getURLParameters('http://url.com/page?name=Adam&surname=Smith');
// {name: 'Adam', surname: 'Smith'}
```
