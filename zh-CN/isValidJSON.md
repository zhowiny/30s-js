---
title: 字符串是有效的 JSON(String is valid JSON)
tags: type
expertise: intermediate
cover: blog_images/italian-horizon.jpg
firstSeen: 2017-12-31T14:53:01+02:00
lastUpdated: 2020-10-18T13:49:49+03:00
---

### 检查提供的字符串是否是有效的 JSON。
> Checks if the provided string is a valid JSON.

- 使用 `JSON.parse()` 和 `try...catch` 块来检查提供的字符串是否是有效的 JSON。

```js
const isValidJSON = str => {
  try {
    JSON.parse(str);
    return true;
  } catch (e) {
    return false;
  }
};
```

```js
isValidJSON('{"name":"Adam","age":20}'); // true
isValidJSON('{"name":"Adam",age:"20"}'); // false
isValidJSON(null); // true
```
