---
title: 数组已排序(Array is sorted)
tags: array
expertise: intermediate
cover: blog_images/italian-horizon.jpg
firstSeen: 2018-01-01T19:30:14+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 检查数值数组是否已排序。
> Checks if a numeric array is sorted.

- 计算第一对相邻数组元素的排序 `direction`。
- 如果给定数组为空、只有一个元素或任何一对相邻数组元素的 `direction` 发生变化，则返回 `0`。
- 使用 `Math.sign()` 将`direction` 的最终值转换为`-1`（降序）或`1`（升序）。

```js
const isSorted = arr => {
  if (arr.length <= 1) return 0;
  const direction = arr[1] - arr[0];
  for (let i = 2; i < arr.length; i++) {
    if ((arr[i] - arr[i - 1]) * direction < 0) return 0;
  }
  return Math.sign(direction);
};
```

```js
isSorted([0, 1, 2, 2]); // 1
isSorted([4, 3, 2]); // -1
isSorted([4, 3, 5]); // 0
isSorted([4]); // 0
```
