---
title: 生成指定长度的数组(Generate items)
tags: array,function
expertise: intermediate
cover: blog_images/generator.jpg
firstSeen: 2020-10-09T20:41:21+03:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

### 使用给定函数生成具有给定数量项目的数组。
> Generates an array with the given amount of items, using the given function.

- 使用 `Array.from()` 创建一个特定长度的空数组，使用每个新创建元素的索引调用 `fn`。
- 回调接受一个参数 - 每个元素的索引。

```js
const generateItems = (n, fn) => Array.from({ length: n }, (_, i) => fn(i));
```

```js
generateItems(10, Math.random);
// [0.21, 0.08, 0.40, 0.96, 0.96, 0.24, 0.19, 0.96, 0.42, 0.70]
```
