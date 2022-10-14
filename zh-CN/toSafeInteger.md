---
title: 值转安全整数(Value to safe integer)
tags: math
expertise: beginner
cover: blog_images/mask-quiet.jpg
firstSeen: 2018-01-08T17:12:46+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

# 将值转换为安全整数。
> Converts a value to a safe integer.

- 使用 `Math.max()` 和 `Math.min()` 找到最接近的安全值。
- 使用 `Math.round()` 转换为整数。

```js
const toSafeInteger = num =>
  Math.round(
    Math.max(Math.min(num, Number.MAX_SAFE_INTEGER), Number.MIN_SAFE_INTEGER)
  );
```

```js
toSafeInteger('3.2'); // 3
toSafeInteger(Infinity); // 9007199254740991
```
