---
title: 数字到货币字符串(Number to currency string)
tags: math,string
expertise: intermediate
cover: blog_images/planning.jpg
firstSeen: 2018-01-27T17:15:48+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 接受一个数字并以指定的货币格式返回它。
> Takes a number and returns it in the specified currency formatting.

- 使用 `Intl.NumberFormat` 启用国家/货币敏感格式。

```js
const toCurrency = (n, curr, LanguageFormat = undefined) =>
  Intl.NumberFormat(LanguageFormat, {
    style: 'currency',
    currency: curr,
  }).format(n);
```

```js
toCurrency(123456.789, 'EUR');
// €123,456.79  | currency: Euro | currencyLangFormat: Local
toCurrency(123456.789, 'USD', 'en-us');
// $123,456.79  | currency: US Dollar | currencyLangFormat: English (United States)
toCurrency(123456.789, 'USD', 'fa');
// ۱۲۳٬۴۵۶٫۷۹ ؜$ | currency: US Dollar | currencyLangFormat: Farsi
toCurrency(322342436423.2435, 'JPY');
// ¥322,342,436,423 | currency: Japanese Yen | currencyLangFormat: Local
toCurrency(322342436423.2435, 'JPY', 'fi');
// 322 342 436 423 ¥ | currency: Japanese Yen | currencyLangFormat: Finnish
```
