---
title: 线性搜索(Linear search)
tags: algorithm,array
expertise: beginner
author: maciv
cover: blog_images/coworking-space.jpg
firstSeen: 2020-12-28T12:07:53+02:00
lastUpdated: 2020-12-28T12:07:53+02:00
---

### 使用线性搜索算法查找数组中给定元素的第一个索引。
> Finds the first index of a given element in an array using the linear search algorithm.

- 使用 `for...in` 循环遍历给定数组的索引。
- 检查相应索引中的元素是否等于 `item`。
- 如果找到元素，则返回索引，使用一元 `+` 运算符将其从字符串转换为数字。
- 如果遍历整个数组后未找到元素，则返回 `-1`。

```js
const linearSearch = (arr, item) => {
  for (const i in arr) {
    if (arr[i] === item) return +i;
  }
  return -1;
};
```

```js
linearSearch([2, 9, 9], 9); // 1
linearSearch([2, 9, 9], 7); // -1
```
