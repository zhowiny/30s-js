---
title: 卢恩检查(Luhn check)
tags: math,algorithm
expertise: advanced
cover: blog_images/blank-card.jpg
excerpt: Implements the Luhn Algorithm, used to validate a variety of identification numbers.
firstSeen: 2018-01-03T11:02:35+02:00
lastUpdated: 2022-01-30T13:37:39+02:00
---

# 实现 [Luhn 算法](https://en.wikipedia.org/wiki/Luhn_algorithm) 用于验证各种识别号码，例如信用卡号码、IMEI 号码、国家提供商标识符号码等。
> Implements the [Luhn Algorithm](https://en.wikipedia.org/wiki/Luhn_algorithm) used to validate a variety of identification numbers, such as credit card numbers, IMEI numbers, National Provider Identifier numbers etc.

- 使用 `String.prototype.split()`、`Array.prototype.reverse()` 和 `Array.prototype.map()` 结合 `parseInt()` 来获取数字数组。
- 使用 `Array.prototype.shift()` 获取最后一位。
- 使用 `Array.prototype.reduce()` 来实现 Luhn 算法。
- 如果 `sum` 可以被 `10` 整除，则返回 `true`，否则返回 `false`。
- [卢恩算法(维基百科)](https://zh.wikipedia.org/zh-cn/%E5%8D%A2%E6%81%A9%E7%AE%97%E6%B3%95)
- [Luhn算法(百度百科)](https://baike.baidu.com/item/Luhn%E7%AE%97%E6%B3%95/22799984)

```js
const luhnCheck = num => {
  const arr = (num + '')
    .split('')
    .reverse()
    .map(x => parseInt(x));
  const lastDigit = arr.shift();
  let sum = arr.reduce(
    (acc, val, i) => (i % 2 !== 0 ? acc + val : acc + ((val *= 2) > 9 ? val - 9 : val)),
    0
  );
  sum += lastDigit;
  return sum % 10 === 0;
};
```

```js
luhnCheck('4485275742308327'); // true
luhnCheck(6011329933655299); //  true
luhnCheck(123456789); // false
```
