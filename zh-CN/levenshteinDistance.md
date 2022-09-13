---
title: 莱文斯坦距离(Levenshtein distance)
tags: string,algorithm
expertise: intermediate
author: chalarangelo
cover: blog_images/armchair.jpg
firstSeen: 2020-12-27T19:49:12+02:00
lastUpdated: 2020-12-29T16:27:50+02:00
---

### 使用 [Levenshtein distance](https://en.wikipedia.org/wiki/Levenshtein_distance) 算法计算两个字符串之间的差异。
> Calculates the difference between two strings, using the [Levenshtein distance](https://en.wikipedia.org/wiki/Levenshtein_distance) algorithm.

- 如果两个字符串中的任何一个的 `length` 为零，则返回另一个字符串的 `length` 。
- 使用 `for` 循环迭代目标字符串的字母，使用嵌套的 `for` 循环迭代源字符串的字母。
- 计算在目标和源中分别替换与 `i - 1` 和 `j - 1` 对应的字母的成本（如果它们相同，则为 `0`，否则为 `1`）。
- 使用 `Math.min()` 填充 2D 数组中的每个元素，上面的单元格的最小值增加 1，左侧的单元格增加 1，或者左上角的单元格增加先前计算的成本。
- 返回生成数组的最后一行的最后一个元素。

```js
const levenshteinDistance = (s, t) => {
  if (!s.length) return t.length;
  if (!t.length) return s.length;
  const arr = [];
  for (let i = 0; i <= t.length; i++) {
    arr[i] = [i];
    for (let j = 1; j <= s.length; j++) {
      arr[i][j] =
        i === 0
          ? j
          : Math.min(
              arr[i - 1][j] + 1,
              arr[i][j - 1] + 1,
              arr[i - 1][j - 1] + (s[j - 1] === t[i - 1] ? 0 : 1)
            );
    }
  }
  return arr[t.length][s.length];
};
```

```js
levenshteinDistance('duck', 'dark'); // 2
```
