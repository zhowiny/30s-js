---
title: 过滤唯一的数组值(Filter unique array values)
tags: array
expertise: beginner
author: maciv
cover: blog_images/tulips-and-reeds.jpg
firstSeen: 2020-11-02T19:41:00+02:00
lastUpdated: 2020-11-02T19:41:00+02:00
---

### 创建一个过滤掉唯一值的数组。
> Creates an array with the unique values filtered out.

- 使用 `Set` 构造函数和扩展运算符 (`...`) 在 `arr` 中创建唯一值数组。
- 使用 `Array.prototype.filter()` 创建一个仅包含非唯一值的数组。

```js
const filterUnique = arr =>
  [...new Set(arr)].filter(i => arr.indexOf(i) !== arr.lastIndexOf(i));
```

```js
filterUnique([1, 2, 2, 3, 4, 4, 5]); // [2, 4]
```
