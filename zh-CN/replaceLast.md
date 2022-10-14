---
title: 替换最后一次出现字符串(Replace last occuerence in string)
tags: string,regexp
expertise: advanced
author: chalarangelo
cover: blog_images/waves.jpg
firstSeen: 2021-04-22T09:01:22+03:00
lastUpdated: 2021-04-22T09:01:22+03:00
---

# 替换字符串中最后一次出现的模式。
> Replaces the last occurrence of a pattern in a string.

- 使用 `typeof` 来确定 `pattern` 是字符串还是正则表达式。
- 如果 `pattern` 是字符串，则将其用作 `match`。
- 否则，使用 `RegExp` 构造函数创建一个新的正则表达式，使用 `pattern` 的 `RegExp.prototype.source` 并向其添加 `'g'` 标志。 使用 `String.prototype.match()` 和 `Array.prototype.slice()` 获取最后一个匹配项（如果有）。
- 使用 `String.prototype.lastIndexOf()` 查找字符串中最后一次出现的匹配项。
- 如果找到匹配项，使用 `String.prototype.slice()` 和模板文字将匹配的子字符串替换为给定的 `replacement`。
- 如果未找到匹配项，则返回原始字符串。

```js
const replaceLast = (str, pattern, replacement) => {
  const match =
    typeof pattern === 'string'
      ? pattern
      : (str.match(new RegExp(pattern.source, 'g')) || []).slice(-1)[0];
  if (!match) return str;
  const last = str.lastIndexOf(match);
  return last !== -1
    ? `${str.slice(0, last)}${replacement}${str.slice(last + match.length)}`
    : str;
};
```

```js
replaceLast('abcabdef', 'ab', 'gg'); // 'abcggdef'
replaceLast('abcabdef', /ab/, 'gg'); // 'abcggdef'
replaceLast('abcabdef', 'ad', 'gg'); // 'abcabdef'
replaceLast('abcabdef', /ad/, 'gg'); // 'abcabdef'
```
