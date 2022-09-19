---
title: 去除重音符号(Remove accents)
tags: string
expertise: beginner
cover: blog_images/pink-flowers.jpg
firstSeen: 2020-10-04T02:23:40+03:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

### 从字符串中删除重音符号。
> Removes accents from strings.

- 使用 `String.prototype.normalize()` 将字符串转换为规范化的 Unicode 格式。
- 使用 `String.prototype.replace()` 将给定 Unicode 范围内的变音符号替换为空字符串。

```js
const removeAccents = str =>
  str.normalize('NFD').replace(/[\u0300-\u036f]/g, '');
```

```js
removeAccents('Antoine de Saint-Exupéry'); // 'Antoine de Saint-Exupery'
```
