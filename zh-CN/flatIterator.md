---
title: 展开迭代器(Flat iterator)
tags: array,iterator,generator
expertise: advanced
author: chalarangelo
cover: blog_images/balloons.jpg
firstSeen: 2022-03-09T05:00:00-04:00
---

### 创建一个生成器，该生成器对可迭代的、扁平化的嵌套可迭代对象进行迭代。
> Creates a generator that iterates over an iterable, flattening nested iterables.

- 使用递归。
- 使用 `for...of` 循环来迭代给定可迭代对象的值。
- 使用 `Symbol.iterator` 检查每个值是否是可迭代的。 如果是，请使用 `yield*` 表达式递归地委托给相同的生成器函数。 否则，`yield` 当前值。

```js
const flatIterator = function* (itr) {
  for (let item of itr) {
    if (item[Symbol.iterator]) yield* flatIterator(item);
    else yield item;
  }
};
```

```js
const arr = [1, 2, [3, 4], [5, [6, [7], 8]], 9, new Set([10, 11])];

[...flatIterator(arr)]; // 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11

arr.flat(Infinity); // [1, 2, 3, ..., Set(2)]
```
