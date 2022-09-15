---
title: 基于属性顺序的对象数组排序(Order array of objects based on property order)
tags: array,object
expertise: intermediate
cover: blog_images/san-francisco-skyline.jpg
firstSeen: 2020-10-04T12:11:10+03:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 根据提供的有序数组对按属性排序的对象数组进行排序。
> Sorts an array of objects, ordered by a property, based on the array of orders provided.

- 使用 `Array.prototype.reduce()` 从 `order` 数组创建一个对象，其中值作为键，它们的原始索引作为值。
- 使用 `Array.prototype.sort()` 对给定数组进行排序，跳过 `order` 数组中 `prop` 为空或不为空的元素。

```js
const orderWith = (arr, prop, order) => {
  const orderValues = order.reduce((acc, v, i) => {
    acc[v] = i;
    return acc;
  }, {});
  return [...arr].sort((a, b) => {
    if (orderValues[a[prop]] === undefined) return 1;
    if (orderValues[b[prop]] === undefined) return -1;
    return orderValues[a[prop]] - orderValues[b[prop]];
  });
};
```

```js
const users = [
  { name: 'fred', language: 'Javascript' },
  { name: 'barney', language: 'TypeScript' },
  { name: 'frannie', language: 'Javascript' },
  { name: 'anna', language: 'Java' },
  { name: 'jimmy' },
  { name: 'nicky', language: 'Python' },
];
orderWith(users, 'language', ['Javascript', 'TypeScript', 'Java']);
/*
[
  { name: 'fred', language: 'Javascript' },
  { name: 'frannie', language: 'Javascript' },
  { name: 'barney', language: 'TypeScript' },
  { name: 'anna', language: 'Java' },
  { name: 'jimmy' },
  { name: 'nicky', language: 'Python' }
]
*/
```
