---
title: 使用反向范围初始化数组(Initialize array with reversed range)
tags: array
expertise: intermediate
cover: blog_images/interior-4.jpg
firstSeen: 2018-01-16T17:09:39+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

### 初始化一个数组，其中包含指定范围内的数字（反向），其中 `start` 和 `end` 包含它们的共同点 `step`。
> Initializes an array containing the numbers in the specified range (in reverse) where `start` and `end` are inclusive with their common difference `step`.

- 使用 `Array.from()` 创建所需长度的数组，`(end - start + 1) / step`。
- 使用 `Array.prototype.map()` 用给定范围内的所需值填充数组。
- 省略第二个参数“start”，使用默认值“0”。
- 省略最后一个参数 `step`，使用默认值 `1`。

```js
const initializeArrayWithRangeRight = (end, start = 0, step = 1) =>
  Array.from({ length: Math.ceil((end + 1 - start) / step) }).map(
    (v, i, arr) => (arr.length - i - 1) * step + start
  );
```

```js
initializeArrayWithRangeRight(5); // [5, 4, 3, 2, 1, 0]
initializeArrayWithRangeRight(7, 3); // [7, 6, 5, 4, 3]
initializeArrayWithRangeRight(9, 0, 2); // [8, 6, 4, 2, 0]
```
