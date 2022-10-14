---
title: 将数组加入字符串(Join array into string)
tags: array
expertise: intermediate
cover: blog_images/couch-laptop.jpg
firstSeen: 2018-01-01T12:18:40+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 将数组的所有元素连接成一个字符串并返回此字符串。使用分隔符和结束分隔符。
> Joins all elements of an array into a string and returns this string.
> Uses a separator and an end separator.

- 使用 `Array.prototype.reduce()` 将元素组合成一个字符串。
- 省略第二个参数 `separator`，使用默认分隔符 `','`。
- 省略第三个参数 `end`，默认使用与 `separator` 相同的值。

```js

const join = (arr, separator = ',', end = separator) =>
  arr.reduce(
    (acc, val, i) =>
      i === arr.length - 2
        ? acc + val + end
        : i === arr.length - 1
          ? acc + val
          : acc + val + separator,
    ''
  );
```

```js
join(['pen', 'pineapple', 'apple', 'pen'],',','&'); // 'pen,pineapple,apple&pen'
join(['pen', 'pineapple', 'apple', 'pen'], ','); // 'pen,pineapple,apple,pen'
join(['pen', 'pineapple', 'apple', 'pen']); // 'pen,pineapple,apple,pen'
```
