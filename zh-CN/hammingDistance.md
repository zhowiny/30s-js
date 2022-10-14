---
title: 汉明距离(Hamming distance)
tags: math,algorithm
expertise: intermediate
cover: blog_images/colorful-lounge.jpg
firstSeen: 2017-12-17T17:55:51+02:00
lastUpdated: 2020-12-28T13:49:24+02:00
---

# 计算两个值之间的汉明距离。
> Calculates the Hamming distance between two values.

- 使用 XOR 运算符 (`^`) 查找两个数字之间的位差。
- 使用 `Number.prototype.toString()` 转换为二进制字符串。
- 使用 `String.prototype.match()` 计算并返回字符串中 `1` 的数量。
- [汉明距离(维基百科)](https://zh.wikipedia.org/zh-cn/%E6%B1%89%E6%98%8E%E8%B7%9D%E7%A6%BB)
- [汉明距离(百度百科)](https://baike.baidu.com/item/%E6%B1%89%E6%98%8E%E8%B7%9D%E7%A6%BB/475174)

```js
const hammingDistance = (num1, num2) =>
  ((num1 ^ num2).toString(2).match(/1/g) || '').length;
```

```js
hammingDistance(2, 3); // 1
```
