---
title: 检查字符串是 `yes` 或者 `no` (Check yes/no string)
tags: string,regexp
expertise: intermediate
unlisted: true
cover: blog_images/mask-quiet.jpg
firstSeen: 2017-12-30T18:35:54+02:00
lastUpdated: 2021-01-04T13:04:15+02:00
---

# 如果字符串是 `'y'`/`'yes'` 则返回 `true` 或如果字符串是 `'n'`/`'no'` 则返回 `false`。
> Returns `true` if the string is `'y'`/`'yes'` or `false` if the string is `'n'`/`'no'`.

- 使用 `RegExp.prototype.test()` 检查字符串的计算结果是否为 `'y'`/`'yes'` 或 `'n'`/`'no'`。
- 省略第二个参数 `def` 以将默认值设置为 `'no'`。

```js
const yesNo = (val, def = false) =>
  /^(y|yes)$/i.test(val) ? true : /^(n|no)$/i.test(val) ? false : def;
```

```js
yesNo('Y'); // true
yesNo('yes'); // true
yesNo('No'); // false
yesNo('Foo', true); // true
```
