---
title: 对象转查询字符串(Object to query string)
tags: object
expertise: advanced
cover: blog_images/standing-stones.jpg
firstSeen: 2019-10-11T23:16:05+03:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 从给定对象的键值对生成查询字符串。
> Generates a query string from the key-value pairs of the given object.

- 在 `Object.entries()` 上使用 `Array.prototype.reduce()` 从 `queryParameters` 创建查询字符串。
- 根据 `queryString` 的长度确定 `symbol` 是 `?` 还是 `&`。
- 只有当它是一个字符串时，才将 `val` 连接到 `queryString`。
- 当 `queryParameters` 为假时，返回 `queryString` 或空字符串。

```js
const objectToQueryString = queryParameters => {
  return queryParameters
    ? Object.entries(queryParameters).reduce(
        (queryString, [key, val], index) => {
          const symbol = queryString.length === 0 ? '?' : '&';
          queryString +=
            typeof val === 'string' ? `${symbol}${key}=${val}` : '';
          return queryString;
        },
        ''
      )
    : '';
};
```

```js
objectToQueryString({ page: '1', size: '2kg', key: undefined });
// '?page=1&size=2kg'
```
