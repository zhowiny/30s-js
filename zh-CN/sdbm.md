---
title: 将字符串哈希成数字(Hash string into number)
tags: math
expertise: intermediate
cover: blog_images/dark-leaves.jpg
firstSeen: 2017-12-27T17:12:34+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 将输入字符串哈希成一个整数。
> Hashes the input string into a whole number.

- 使用 `String.prototype.split()` 和 `Array.prototype.reduce()` 利用位移，创建输入字符串的哈希。

```js
const sdbm = str => {
  let arr = str.split('');
  return arr.reduce(
    (hashCode, currentVal) =>
      (hashCode =
        currentVal.charCodeAt(0) +
        (hashCode << 6) +
        (hashCode << 16) -
        hashCode),
    0
  );
};
```

```js
sdbm('name'); // -3521204949
```
