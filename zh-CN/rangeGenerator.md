---
title: 范围生成器(Range generator)
tags: function,generator
expertise: advanced
author: chalarangelo
cover: blog_images/dark-leaves-6.jpg
firstSeen: 2020-10-11T17:05:55+03:00
lastUpdated: 2020-10-11T17:05:55+03:00
---

### 创建一个生成器，使用给定的步骤生成给定范围内的所有值。
> Creates a generator, that generates all values in the given range using the given step.

- 使用 `while` 循环从 `start` 到 `end` 迭代，使用 `yield` 返回每个值，然后按 `step` 递增。
- 省略第三个参数 `step`，使用默认值 `1`。

```js
const rangeGenerator = function* (start, end, step = 1) {
  let i = start;
  while (i < end) {
    yield i;
    i += step;
  }
};
```

```js
for (let i of rangeGenerator(6, 10)) console.log(i);
// Logs 6, 7, 8, 9
```
