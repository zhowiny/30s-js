---
title: 数组分区(Partition array)
tags: array,object
expertise: advanced
cover: blog_images/people-on-beach.jpg
firstSeen: 2020-05-20T17:48:13+03:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

### 将 `fn` 应用于 `arr` 中的每个值，每次提供的函数返回一个新值时将其拆分。
> Applies `fn` to each value in `arr`, splitting it each time the provided function returns a new value.

- 将 `Array.prototype.reduce()` 与一个累加器对象一起使用，该对象将保存结果数组和从 `fn` 返回的最后一个值。
- 使用 `Array.prototype.push()` 将 `arr` 中的每个值添加到累加器数组中的适当分区。

```js
const partitionBy = (arr, fn) =>
  arr.reduce(
    ({ res, last }, v, i, a) => {
      const next = fn(v, i, a);
      if (next !== last) res.push([v]);
      else res[res.length - 1].push(v);
      return { res, last: next };
    },
    { res: [] }
  ).res;
```

```js
const numbers = [1, 1, 3, 3, 4, 5, 5, 5];
partitionBy(numbers, n => n % 2 === 0); // [[1, 1, 3, 3], [4], [5, 5, 5]]
partitionBy(numbers, n => n); // [[1, 1], [3, 3], [4], [5, 5, 5]]
```
