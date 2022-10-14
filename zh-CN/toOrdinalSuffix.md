---
title: 数字到序数指示符后缀(Number to ordinal suffix)
tags: math
expertise: intermediate
cover: blog_images/tram-car-2.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-11-13T19:49:57+02:00
---

# 接受一个数字并将其作为带有正确序数指示符后缀的字符串返回。
> Takes a number and returns it as a string with the correct ordinal indicator suffix.

- 使用取模运算符（`%`）求个位数和十位数的值。
- 查找匹配的序数模式数字。
- 如果在 teens 模式中找到数字，使用 teens 序数。

```js
const toOrdinalSuffix = num => {
  const int = parseInt(num),
    digits = [int % 10, int % 100],
    ordinals = ['st', 'nd', 'rd', 'th'],
    oPattern = [1, 2, 3, 4],
    tPattern = [11, 12, 13, 14, 15, 16, 17, 18, 19];
  return oPattern.includes(digits[0]) && !tPattern.includes(digits[1])
    ? int + ordinals[digits[0] - 1]
    : int + ordinals[3];
};
```

```js
toOrdinalSuffix('123'); // '123rd'
```
