---
title: 数组的头部(Head of array)
tags: array
expertise: beginner
cover: blog_images/clay-pot-horizon.jpg
firstSeen: 2017-12-17T16:41:31+02:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 返回数组的头部。
> Returns the head of an array.

- 检查 `arr` 是否真实且具有 `length` 属性。
- 如果可能，使用 `arr[0]` 返回第一个元素，否则返回 `undefined`。

```js
const head = arr => (arr && arr.length ? arr[0] : undefined);
```

```js
head([1, 2, 3]); // 1
head([]); // undefined
head(null); // undefined
head(undefined); // undefined
```
