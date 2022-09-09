---
title: 用范围初始化数组(Initialize array with range)
tags: array
expertise: intermediate
cover: blog_images/white-flower.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 初始化一个包含指定范围内的数字的数组，其中 `start` 和 `end` 包含它们的共同点 `step`。
> Initializes an array containing the numbers in the specified range where `start` and `end` are inclusive with their common difference `step`.

- 使用 `Array.from()` 创建所需长度的数组。
- 使用 `(end - start + 1) / step` 和 map 函数在给定范围内使用所需值填充数组。
- 省略第二个参数 `start`，使用默认值 `0`。
- 省略最后一个参数 `step`，使用默认值 `1`。

```js
const initializeArrayWithRange = (end, start = 0, step = 1) =>
  Array.from(
    { length: Math.ceil((end - start + 1) / step) },
    (_, i) => i * step + start
  );
```

```js
initializeArrayWithRange(5); // [0, 1, 2, 3, 4, 5]
initializeArrayWithRange(7, 3); // [3, 4, 5, 6, 7]
initializeArrayWithRange(9, 0, 2); // [0, 2, 4, 6, 8]
```
