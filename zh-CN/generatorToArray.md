---
title: 可迭代对象转数组(Generator to array)
tags: function,array,generator
expertise: beginner
author: chalarangelo
cover: blog_images/messy-papers.jpg
firstSeen: 2020-12-31T13:22:18+02:00
lastUpdated: 2020-12-31T13:22:18+02:00
---

### 将生成器函数的输出转换为数组。
> Converts the output of a generator function to an array.

- 使用扩展运算符 (`...`) 将生成器函数的输出转换为数组。

```js
const generatorToArray = gen => [...gen];
```

```js
const s = new Set([1, 2, 1, 3, 1, 4]);
generatorToArray(s.entries()); // [[ 1, 1 ], [ 2, 2 ], [ 3, 3 ], [ 4, 4 ]]
```
