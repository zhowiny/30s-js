---
title: 复数字符串(Pluralize string)
tags: string
expertise: advanced
cover: blog_images/shell-focus.jpg
firstSeen: 2018-01-03T13:17:19+02:00
lastUpdated: 2020-10-22T20:24:04+03:00
---

# 根据输入数字返回单词的单数或复数形式，如果提供的话，使用可选字典。
> Returns the singular or plural form of the word based on the input number, using an optional dictionary if supplied.

- 使用闭包来定义一个函数，根据 `num` 的值将给定的 `word` 复数。
- 如果 `num` 是 `-1` 或 `1`，则返回单词的单数形式。
- 如果 `num` 是任何其他数字，则返回 `plural` 形式。
- 省略第三个参数 `plural`，以使用默认的单数词 + `s`，或在必要时提供自定义的复数 `word`。
- 如果第一个参数是 `object`，则返回一个函数，该函数可以使用提供的字典来解析单词的正确复数形式。

```js
const pluralize = (val, word, plural = word + 's') => {
  const _pluralize = (num, word, plural = word + 's') =>
    [1, -1].includes(Number(num)) ? word : plural;
  if (typeof val === 'object')
    return (num, word) => _pluralize(num, word, val[word]);
  return _pluralize(val, word, plural);
};
```

```js
pluralize(0, 'apple'); // 'apples'
pluralize(1, 'apple'); // 'apple'
pluralize(2, 'apple'); // 'apples'
pluralize(2, 'person', 'people'); // 'people'

const PLURALS = {
  person: 'people',
  radius: 'radii'
};
const autoPluralize = pluralize(PLURALS);
autoPluralize(2, 'person'); // 'people'
```
