---
title: 对象的顺序数组(Order array of objects)
tags: object,array
expertise: advanced
cover: blog_images/volcano-sunset.jpg
firstSeen: 2017-12-20T11:33:20+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

# 对对象数组进行排序，按属性和顺序排序。
> Sorts an array of objects, ordered by properties and orders.

- 在 `props` 数组上使用 `Array.prototype.sort()`、`Array.prototype.reduce()`，默认值为 `0`。
- 根据提供的顺序使用数组解构来交换属性位置。
- 如果没有提供 `orders` 数组，默认按 `'asc'` 排序。

```js
const orderBy = (arr, props, orders) =>
  [...arr].sort((a, b) =>
    props.reduce((acc, prop, i) => {
      if (acc === 0) {
        const [p1, p2] =
          orders && orders[i] === 'desc'
            ? [b[prop], a[prop]]
            : [a[prop], b[prop]];
        acc = p1 > p2 ? 1 : p1 < p2 ? -1 : 0;
      }
      return acc;
    }, 0)
  );
```

```js
const users = [
  { name: 'fred', age: 48 },
  { name: 'barney', age: 36 },
  { name: 'fred', age: 40 },
];
orderBy(users, ['name', 'age'], ['asc', 'desc']);
// [{name: 'barney', age: 36}, {name: 'fred', age: 48}, {name: 'fred', age: 40}]
orderBy(users, ['name', 'age']);
// [{name: 'barney', age: 36}, {name: 'fred', age: 40}, {name: 'fred', age: 48}]
```
