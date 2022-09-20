---
title: 整数转罗马数字(Integer to roman numeral)
tags: math,string
expertise: intermediate
cover: blog_images/ancient-greek-building.jpg
firstSeen: 2020-10-06T19:56:22+03:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

### 将整数转换为其罗马数字表示。接受 `1` 和 `3999` 之间的值（包括两者）。
> Converts an integer to its roman numeral representation.
> Accepts value between `1` and `3999` (both inclusive).

- 创建一个包含（罗马值，整数）形式的 2 值数组的查找表。
- 使用 `Array.prototype.reduce()` 循环 `lookup` 中的值，并反复将 `num` 除以该值。
- 使用 `String.prototype.repeat()` 将罗马数字表示添加到累加器。

```js
const toRomanNumeral = num => {
  const lookup = [
    ['M', 1000],
    ['CM', 900],
    ['D', 500],
    ['CD', 400],
    ['C', 100],
    ['XC', 90],
    ['L', 50],
    ['XL', 40],
    ['X', 10],
    ['IX', 9],
    ['V', 5],
    ['IV', 4],
    ['I', 1],
  ];
  return lookup.reduce((acc, [k, v]) => {
    acc += k.repeat(Math.floor(num / v));
    num = num % v;
    return acc;
  }, '');
};
```

```js
toRomanNumeral(3); // 'III'
toRomanNumeral(11); // 'XI'
toRomanNumeral(1998); // 'MCMXCVIII'
```
