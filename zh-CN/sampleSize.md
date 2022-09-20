---
title: 数组中的 N 个随机元素(N random elements in array)
tags: array,random
expertise: intermediate
cover: blog_images/tree-roots.jpg
firstSeen: 2017-12-31T13:56:28+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 从数组中获取唯一索引的 `n` 个随机元素，直到数组的大小。
> Gets `n` random elements at unique keys from an array up to the size of the array.

- 使用 [Fisher-Yates 洗牌算法](./shuffle) 对数组进行洗牌。
- 使用 `Array.prototype.slice()` 获取第一个 `n` 元素。
- 省略第二个参数 `n`，只从数组中随机获取一个元素。

```js
const sampleSize = ([...arr], n = 1) => {
  let m = arr.length;
  while (m) {
    const i = Math.floor(Math.random() * m--);
    [arr[m], arr[i]] = [arr[i], arr[m]];
  }
  return arr.slice(0, n);
};
```

```js
sampleSize([1, 2, 3], 2); // [3, 1]
sampleSize([1, 2, 3], 4); // [2, 3, 1]
```
