---
title: 字符串全排列(String permutations)
tags: string,recursion
expertise: advanced
cover: blog_images/mac-and-coffee.jpg
firstSeen: 2018-02-19T15:47:47+02:00
lastUpdated: 2020-11-15T17:13:42+02:00
---

# 生成字符串的所有排列（包含重复项）。
> Generates all permutations of a string (contains duplicates).

- 使用递归。
- 对于给定字符串中的每个字母，为其其余字母创建所有部分排列。
- 使用 `Array.prototype.map()` 将字母与每个部分排列组合。
- 使用 `Array.prototype.reduce()` 将所有排列组合到一个数组中。
- 基本情况是 `String.prototype.length` 等于 `2` 或 `1`。
- ⚠️ **警告**：执行时间随每个字符呈指数增长。 任何超过 8 到 10 个字符的字符都会导致您的环境在尝试解决所有不同组合时挂起。

```js
const stringPermutations = str => {
  if (str.length <= 2) return str.length === 2 ? [str, str[1] + str[0]] : [str];
  return str
    .split('')
    .reduce(
      (acc, letter, i) =>
        acc.concat(
          stringPermutations(str.slice(0, i) + str.slice(i + 1)).map(
            val => letter + val
          )
        ),
      []
    );
};
```

```js
stringPermutations('abc'); // ['abc', 'acb', 'bac', 'bca', 'cab', 'cba']
```
