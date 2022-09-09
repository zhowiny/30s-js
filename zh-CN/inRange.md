---
title: 数字在范围内(Number in range)
tags: math
expertise: beginner
cover: blog_images/armchair.jpg
firstSeen: 2017-12-20T18:33:58+02:00
lastUpdated: 2020-11-01T20:50:57+02:00
---

### 检查给定数字是否在给定范围内。
> Checks if the given number falls within the given range.

- 使用算术比较检查给定数字是否在指定范围内。
- 如果没有指定第二个参数 `end`，则范围被认为是从 `0` 到 `start`。

```js
const inRange = (n, start, end = null) => {
  if (end && start > end) [end, start] = [start, end];
  return end == null ? n >= 0 && n < start : n >= start && n < end;
};
```

```js
inRange(3, 2, 5); // true
inRange(3, 4); // true
inRange(2, 3, 5); // false
inRange(3, 2); // false
```
